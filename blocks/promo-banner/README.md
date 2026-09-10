# Promo Banner Block

## Overview

The Promo Banner block renders a heading plus a horizontal list of products from a given commerce category, intended for use as a promotional/featured-products banner. Product data is fetched live via the storefront GraphQL client.

## Configuration

Configuration is read via `readBlockConfig()` from the block's authored table:

- `category-id` - The commerce category ID to fetch products from. Defaults to an empty string if omitted, which will typically return no results from the category filter.
- `heading` - The heading text displayed above the product list. Defaults to `"Featured Products"`.
- `max-products` - The maximum number of products to fetch and display. Defaults to `4`; non-numeric values also fall back to `4`.

## Integration

### GraphQL

The block uses `CS_FETCH_GRAPHQL.fetchGraphQl` (from `scripts/commerce.js`) to query `productSearch`, filtering by `categoryIds` and limiting results with `page_size`. For each product it requests name, SKU, URL key, an image, and (for simple products) the final price.

### Product Links

Product URLs are generated with `getProductLink(urlKey, sku)` from `scripts/commerce.js`, matching the site's standard product link format.

No URL parameters or localStorage are used by this block.

### Events

No events are emitted or listened for by this block.

## Behavior Patterns

### Rendering States

1. **Initialization**: Renders the heading immediately and a "Loading products..." placeholder in the products area.
2. **Loaded**: Replaces the placeholder with a row of product links, each showing image, name, and price (when available).
3. **Empty Results**: If the category query returns no items, renders a "No products found." message.

### User Interaction Flow

Each rendered product is a link (`<a class="promo-banner__product">`) to the product detail page; clicking navigates the user to that product using the standard product link format.

## Error Handling

- **Fetch Failures**: If the GraphQL request throws (network error, bad category, etc.), the error is logged to the console via `console.error('Promo banner: failed to fetch products', error)` and the products area shows "Unable to load products."
- **Missing Image/Price**: Individual products render without an image or price if those fields are absent from the response, rather than failing the whole block.
- **Invalid `max-products`**: Non-numeric or missing values fall back to a default of 4 via `parseInt(...) || 4`.
