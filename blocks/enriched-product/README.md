# Enriched Product Block

## Overview

The Enriched Product block displays a single product card that combines live catalog data (name, image, price) with supplemental "enrichment" data (sustainability score, estimated delivery, enrichment timestamp) fetched from an API Mesh GraphQL endpoint. It is intended for merchandising a single SKU with extra context beyond standard catalog attributes.

## Configuration

Configuration is read via `readBlockConfig()` from the block's authored table:

- `sku` - The product SKU to fetch and render. **Required.** If omitted, the block renders a "No SKU configured for this block." message and does not make any network requests.

## Integration

### API Mesh Endpoint

The block calls a hardcoded API Mesh GraphQL endpoint (`MESH_ENDPOINT` in `enriched-product.js`) with a single query that requests:

- Catalog product data (`products`): name, images, and price (simple product final price or complex product minimum price range)
- Enrichment data (`Enrichment_getProductEnrichment`): sustainability score, estimated delivery, and enrichment timestamp for the given SKU

No URL parameters or localStorage are used by this block.

### Events

No events are emitted or listened for by this block.

## Behavior Patterns

### Rendering States

1. **No SKU**: Renders a message indicating no SKU is configured; no fetch is attempted.
2. **Loading**: Renders a "Loading product details..." placeholder while the mesh request is in flight.
3. **Product Not Found**: If the mesh response contains no matching product, renders a "Product not found." message.
4. **Loaded**: Renders a card with the product image, name, SKU, price, and (if present) enrichment data including a sustainability badge, estimated delivery, and enrichment timestamp.

### Sustainability Badge

The sustainability score is mapped to a label and CSS class:

- `>= 80` - "Excellent" (`badge--excellent`)
- `>= 60` - "Good" (`badge--good`)
- `< 60` - "Fair" (`badge--fair`)

### User Interaction Flow

This block is read-only/display-only; it does not accept user input beyond page load.

## Error Handling

- **Missing SKU**: Short-circuits before any network call and shows a configuration message.
- **Mesh Request Failures**: A non-OK HTTP response throws and is caught, rendering "Unable to load product data." and logging the error to the console.
- **GraphQL Errors**: Errors returned in the GraphQL response payload are logged to the console and thrown, resulting in the same "Unable to load product data." fallback.
- **Missing Enrichment Data**: If enrichment data is absent from the response, the enrichment section (badge, delivery, timestamp) is simply omitted; the base product card still renders.
