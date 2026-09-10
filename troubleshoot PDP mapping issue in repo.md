curl --fail-with-body -sS \
  'https://admin.hlx.page/code/bwpadobe/citisig-product2o/main/*' \
  -H "Authorization: token $AEM_ADMIN_TOKEN" \
  -H "Accept: application/json"


curl --fail-with-body -sS -i -X POST \
  "https://admin.hlx.page/config/bwpadobe/sites/citisig-product2o/public.json" \
  -H "x-auth-token: $AEM_ADMIN_TOKEN" \
  -H "content-type: application/json" \
  --data-binary @FIXED-CitiSig_Configuration.json

curl -v -X POST "https://admin.hlx.page/config/bwpadobe/sites/citisig-product2o/folders.json" \
-H "Content-Type: application/json" \
-H "Authorization: token $AEM_ADMIN_TOKEN" \
-d '{
"/products/": "/products/default"
}'




  curl --fail-with-body -sS \
  -H "x-auth-token: $AEM_ADMIN_TOKEN" \
  "https://admin.hlx.page/config/adobepls/sites/accs-edstraining-test3.json"

  curl --fail-with-body -sS \
  -H "x-auth-token: $AEM_ADMIN_TOKEN" \
  "https://admin.hlx.page/config/adobepls/sites/repoless-first.json"

  curl --fail-with-body -sS \
  -H "x-auth-token: $AEM_ADMIN_TOKEN" \
  "https://admin.hlx.page/config/bwpadobe/sites/frescopa-test.json"

  curl --fail-with-body -sS \
  -H "x-auth-token: $AEM_ADMIN_TOKEN" \
  "https://admin.hlx.page/config/bwpadobe/sites/citisig-product2o.json"


export AEM_ADMIN_TOKEN="eyJhbGciOiJSUzI1NiIsImtpZCI6Ijdzb2k4N3pkb3NJRnc4b19fbVR5a082QlVRNEZBVGhjaHlyNGZqY1dSbWcifQ.eyJlbWFpbCI6IkJlbmppZS5XaGVlbGVyQGFkb2JlLmNvbSIsIm5hbWUiOiJQTFMgUHVibGljIiwidXNlcl9pZCI6IjVBMUI4MUFCNkE1QTc3Q0MwQTQ5NUMxMkBBZG9iZUlEIiwiaW1zVG9rZW4iOiJleUpoYkdjaU9pSlNVekkxTmlJc0luZzFkU0k2SW1sdGMxOXVZVEV0YTJWNUxXRjBMVEV1WTJWeUlpd2lhMmxrSWpvaWFXMXpYMjVoTVMxclpYa3RZWFF0TVNJc0ltbDBkQ0k2SW1GMEluMC5leUpwWkNJNklqRTNPRGd6TmpZME9ERTJOVFpmWm1WbU5tVmtOREV0T1RkbVpTMDBOR1E0TFdJNU9HRXRaRGxoT0RZd05qQm1NamsyWDNWbE1TSXNJblI1Y0dVaU9pSmhZMk5sYzNOZmRHOXJaVzRpTENKamJHbGxiblJmYVdRaU9pSm9aV3hwZUMxaFpHMXBiaUlzSW5WelpYSmZhV1FpT2lJMVFURkNPREZCUWpaQk5VRTNOME5ETUVFME9UVkRNVEpBUVdSdlltVkpSQ0lzSW5OMFlYUmxJam9pWlhsS2FHSkhZMmxQYVVwMVlqSTFiRWx1TUM1bGVVcDNZMjA1ZEdOSVVXbFBhVXB6WWpKa2NHSnBTWE5KYlRsNVdubEpOa2x0Um10aU1rcHNTVzR3TGlJc0ltRnpJam9pYVcxekxXNWhNU0lzSW1GaFgybGtJam9pTlVFeFFqZ3hRVUkyUVRWQk56ZERRekJCTkRrMVF6RXlRRUZrYjJKbFNVUWlMQ0pqZEhBaU9qQXNJbVpuSWpvaU1sbEhVRnBWUTBSV1RFMDFRVVJWUzBaQlVWWkxXRUZCUXpROVBUMDlQVDBpTENKemFXUWlPaUl4TnpnNE16WTJORGd4TURFeFh6ZGpPVEE0WkRaaUxURmpNemt0TkRkbE1pMWhaV0kyTFRkaE9UYzROVE14WlRFMU0xOTFkeklpTENKeWRHbGtJam9pTVRjNE9ETTJOalE0TVRZMU4xOWxOemd4TkdVMVl5MDBOR1JoTFRSbFpEZ3RPR0ZrT0MwNE5ETm1ObVF6WkRNM1pHRmZkV1V4SWl3aWJXOXBJam9pTWpSa1kySTNOVFVpTENKd1ltRWlPaUpOWldSVFpXTk9iMFZXTEV4dmQxTmxZeUlzSW5KMFpXRWlPaUl4TnpnNU5UYzJNRGd4TmpVM0lpd2laWGh3YVhKbGMxOXBiaUk2SWpnMk5EQXdNREF3SWl3aVkzSmxZWFJsWkY5aGRDSTZJakUzT0Rnek5qWTBPREUyTlRjaUxDSnpZMjl3WlNJNklrRmtiMkpsU1VRc2IzQmxibWxrTEhCeWIyWnBiR1VzWlcxaGFXd3NZV0l1YldGdVlXZGxMR2R1WVhZc2IzSm5MbkpsWVdRc2NtVmhaRjl2Y21kaGJtbDZZWFJwYjI1ekxITmxjM05wYjI0c1lXUmthWFJwYjI1aGJGOXBibVp2TG05M2JtVnlUM0puTEdGa1pHbDBhVzl1WVd4ZmFXNW1ieTV3Y205cVpXTjBaV1JRY205a2RXTjBRMjl1ZEdWNGRDeGhaVzB1Wm5KdmJuUmxibVF1WVd4c0luMC5SenM1MnRJaFFoTlFjcWRWeW9uOHJoUkNteUttX2I5d3RjQV83eUNGcXJfdmp6Umpwc3dPZGFoZl84cUpVcG9vWDF5VGJlTzN0MEtJV0lxSXJQVm5YNHpNMFBhczZKekRYSExteGZ1UE92MGR3aTQ4eEJtQmNWUzdiYXZuTGdXbzRKaG1KMXFlYlRpWmVLbXFzNkJKRVp0ejdCeXdjYlNLLTg0Qk9xTTBNbHNBdlVVa09JMmg2LXlZaW5aRXdpMUJVbXBldVJiNU90TWp5WHVzUTJZODZNRXE0anpjNk9ocXBuRDZEcEpxYmJodWFTZTZ3V3dHQmVZdDlSa2hpb1BqOHU1ZFVOSUpVSEswdExGZzVVdXlMLTVjazNfeG1jXzNtM2NKUFJjcmxEcF9VS2FvXzVFWnVoZXNpN2xTOUxOLW1paFhEN0t0MUtnNXhLZE04aFg1MVEiLCJvd25lck9yZyI6bnVsbCwiaWF0IjoxNzg4MzY2NDgxLCJpc3MiOiJodHRwczovL2FkbWluLmhseC5wYWdlLyIsInN1YiI6IiovKiIsImF1ZCI6IjgzYTM2MzU1LWFkMTctNGVkMC04NzAxLWU5OWEzMDIwZjg2YSIsImV4cCI6MTc4ODQ1Mjg4MX0.Qf2Mkwyd-kpQs1r34b4lrm00m6lKywtATZhQ5pluIRaQw1WTGCJJfYVy1lqpt2rCEr5oWN2WO3yFoiONw-8m_QgC_Wy86N6Rn1QkM54sFsCd-u7ZF-U-EMGJ-JmmCde0cH_ck_g4iHzqKViIK9N0ENqCb3SUWFTBEcylOw6d2rfcQ-ebXiq-8nbFfr53ThyrAGNZxffBD3aHfOmQPdeJQAviBhdoMXRznzik0Kq_jZW1uEZ1XtBgW497KLKgUpBGrioYvJp7nv-YVinasp8kpuHCwhaqJuFjCFDKffDfVS7ywPfvfKo2Cq0eQWxbwHTZPLVIfFV2uq_FpdnAWiKFFw"


troubleshoot PDP mapping issue in repoless-first:

export ORG="adobepls"
export FIRST_SITE="accs-edstraining-test3"
export SECOND_SITE="repoless-first"
export CONFIG_FILE="site1-config.json"
export IMS_TOKEN="eyJhbGciOiJSUzI1NiIsImtpZCI6Ijdzb2k4N3pkb3NJRnc4b19fbVR5a082QlVRNEZBVGhjaHlyNGZqY1dSbWcifQ.eyJlbWFpbCI6InRyYWluaW5nZWRzZG9jc0BnbWFpbC5jb20iLCJuYW1lIjoiRURTIFRyYWluaW5nIiwidXNlcl9pZCI6IjIwMTI4M0JCNkEwNjIzMjIwQTQ5NUVEQUBhZTBjMjJlNDY5MTIyODhkNDk1ZmQ1LmUiLCJpbXNUb2tlbiI6ImV5SmhiR2NpT2lKU1V6STFOaUlzSW5nMWRTSTZJbWx0YzE5dVlURXRhMlY1TFdGMExURXVZMlZ5SWl3aWEybGtJam9pYVcxelgyNWhNUzFyWlhrdFlYUXRNU0lzSW1sMGRDSTZJbUYwSW4wLmV5SnBaQ0k2SWpFM09EYzJNRGt6TWpJeU16aGZNall5WmpNeE56UXRPVGcyTkMwME1EUmxMV0pqWXpJdE9EbGxNemsyWVdKbE9UUmpYM1ZsTVNJc0luUjVjR1VpT2lKaFkyTmxjM05mZEc5clpXNGlMQ0pqYkdsbGJuUmZhV1FpT2lKb1pXeHBlQzFoWkcxcGJpSXNJblZ6WlhKZmFXUWlPaUl5TURFeU9ETkNRalpCTURZeU16SXlNRUUwT1RWRlJFRkFZV1V3WXpJeVpUUTJPVEV5TWpnNFpEUTVOV1prTlM1bElpd2ljM1JoZEdVaU9pSmxlVXBvWWtkamFVOXBTblZpTWpWc1NXNHdMbVY1U25kamJUbDBZMGhSYVU5cFNuTmlNbVJ3WW1sSmMwbHRPWGxhZVVrMlNXMUdhMkl5U214SmJqQXVJaXdpWVhNaU9pSnBiWE10Ym1FeElpd2lZV0ZmYVdRaU9pSXdORFEzT0RNeU5EWTVSa05CUkVFME1FRTBPVFZGTVVWQVFXUnZZbVZKUkNJc0ltTjBjQ0k2TUN3aVptY2lPaUl5V0U1UVVsVkRSRlpNVFRWQlJGVkxSa0ZSVmt0WVFVRkROQ0lzSW5OcFpDSTZJakUzT0RjMk1Ea3pNakUyTnpGZk5ERXhPVE01WXpJdE9ERmxZUzAwTURjMkxXRTJOV1F0T0RkaFpUSTJZMll6TlRZNVgzVjNNaUlzSW5KMGFXUWlPaUl4TnpnM05qQTVNekl5TWpNNVh6UmtaVEl4Tm1Zd0xUbGxPVGd0TkRjMVppMDRNemsxTFRjd05XWmlOR00wT1RFeU5GOTFaVEVpTENKdGIya2lPaUppWldNMFpUQXhOQ0lzSW5CaVlTSTZJazFsWkZObFkwNXZSVllzVEc5M1UyVmpJaXdpY25SbFlTSTZJakUzT0RnNE1UZzVNakl5TXpraUxDSmxlSEJwY21WelgybHVJam9pT0RZME1EQXdNREFpTENKelkyOXdaU0k2SWtGa2IySmxTVVFzYjNCbGJtbGtMSEJ5YjJacGJHVXNaVzFoYVd3c1lXSXViV0Z1WVdkbExHZHVZWFlzYjNKbkxuSmxZV1FzY21WaFpGOXZjbWRoYm1sNllYUnBiMjV6TEhObGMzTnBiMjRzWVdSa2FYUnBiMjVoYkY5cGJtWnZMbTkzYm1WeVQzSm5MR0ZrWkdsMGFXOXVZV3hmYVc1bWJ5NXdjbTlxWldOMFpXUlFjbTlrZFdOMFEyOXVkR1Y0ZEN4aFpXMHVabkp2Ym5SbGJtUXVZV3hzSWl3aVkzSmxZWFJsWkY5aGRDSTZJakUzT0RjMk1Ea3pNakl5TXpnaWZRLkhOaG5wSm1WV2x1MzRKSVNDYnVaLUdRQ2hTRnhVVGZ0dzBfbWFkZ3VpZW5qLThJYjNWbmxWeGlQVW5FU2dIX0c4cGlQR0lNa1VXaERJZF9LazNBb09Lb3ViMS1sN2prNmMwOWsycmI5M3hkVlJWZ0V2cnJxNEM5eHplMHpiQVV5T0otaWtObjdXczQwcS1RdnFNS2w3bnp3cDJCSllTcjl1VFdFWk1mWm1qQjJzdzhCTlRLRHM1aXQtY3M3aXZoRW5sTW1RU0k2RUtJenE4WUxjWkEzNkNkM0llZ0xtR21MRVZ0cGkxaTA4TW1nRG95cVBsN2xRZGhmcjFnOHd0MHlmY0FwVldGeVlSUTY4eTFVVDN5alhnbDhrWksxNGg4U1R1RkpSUzY4NjJJUGE5M1lfZy1BUXJ6RXdRazhMMkpnYm1qTVlLRW80UFRnN19mazB1VFV6QSIsIm93bmVyT3JnIjoiQjEzOTIzMUM2OTEyMjg1QzBBNDk1RkJFQEFkb2JlT3JnIiwiaWF0IjoxNzg3NjA5MzIyLCJpc3MiOiJodHRwczovL2FkbWluLmhseC5wYWdlLyIsInN1YiI6IiovKiIsImF1ZCI6IjgzYTM2MzU1LWFkMTctNGVkMC04NzAxLWU5OWEzMDIwZjg2YSIsImV4cCI6MTc4NzY5NTcyMn0.cDW4KsrCu_5ShkC71hLB5_qkyYx3AOJQNHO71kiYsEEQovORoZJezA5pkq5tvX_5tMyLIGS58Wis0T4q0bmoOY0DHNTVhcRDuoN27ji4uh8dQCOeA6wlUZVFVWf8f91-ymEJk-_SD-1HV-EeYsgCroIyOZG_5vMp_z6AU14RWThk79ILCxAvMSKP4Ymrn0Xk09hT-S23vq3aHhgIwVdmc9X7coNYRfbsXGKgyvCONBJaKdAf38V14CShkmqE3HrOA3FqLoQd8vAL1DOYOTR3r64iTPPb4hlG5MJlmk22Crkd7yNjA-UmaGnJ41V8Q9-GGCgc0dP0YdMcd5XR2mHJEw"

curl --fail --silent --show-error \
  --header "x-auth-token: ${IMS_TOKEN}" \
  "https://admin.hlx.page/config/${ORG}/sites/${FIRST_SITE}.json" \
  > "${FIRST_SITE}.json"

curl --fail --silent --show-error \
  --header "x-auth-token: ${IMS_TOKEN}" \
  "https://admin.hlx.page/config/${ORG}/sites/${SECOND_SITE}.json" \
  > "${SECOND_SITE}.json"

jq '{
  version,
  public,
  folders,
  content: {
    source: .content.source,
    overlay: .content.overlay
  }
}' "${FIRST_SITE}.json"

//explore getting more out of the config.json:

jq '{
  version,
  public,
  commerce-endpoint,
  folders,
  content: {
    source: .content.source,
    overlay: .content.overlay
  }
}' "${FIRST_SITE}.json"

jq '{
  version,
  public,
  folders,
  content: {
    source: .content.source,
    overlay: .content.overlay
  }
}' "${SECOND_SITE}.json"


curl --fail --silent --show-error \
  --header "x-auth-token: ${IMS_TOKEN}" \
  "https://admin.hlx.page/config/${ORG}/sites/${SECOND_SITE}.json" \
  | jq '{
      version,
      folders,
      public,
      content: {
        source: .content.source,
        overlay: .content.overlay
      }
    }'

    curl --fail --silent --show-error \
  "https://main--${SECOND_SITE}--${ORG}.aem.page/config.json" \
  -o "/tmp/${SECOND_SITE}-config.json"

jq '{
  public,
  commerce: .public.default
}' "/tmp/${SECOND_SITE}-config.json"


curl --location \
  --fail --silent --show-error \
  --output /dev/null \
  --write-out "HTTP status: %{http_code}\n" \
  "https://main--${SECOND_SITE}--${ORG}.aem.page/products/default"


curl --fail --silent --show-error \
  --header "x-auth-token: ${IMS_TOKEN}" \
  "https://admin.hlx.page/config/${ORG}/sites/${SECOND_SITE}.json" \
  > "${SECOND_SITE}.json"

cp "${SECOND_SITE}.json" "${SECOND_SITE}.backup.json"


jq '
  .version = (.version + 1)
  | .folders = {
      "/products/": "/products/default"
    }
' "${SECOND_SITE}.json" > "${SECOND_SITE}.updated.json"


curl --fail --silent --show-error \
  --request POST \
  --header "x-auth-token: ${IMS_TOKEN}" \
  --header "content-type: application/json" \
  --data-binary @"${SECOND_SITE}.updated.json" \
  "https://admin.hlx.page/config/${ORG}/sites/${SECOND_SITE}.json"