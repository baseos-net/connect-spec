# Pairing

`POST https://baseos.net/api/v1/connect/pair`

Send either a one-time `pair_code` from BaseOS, or an `auth_code` plus `code_verifier` from the WordPress handoff. Always send `site_url` and `receiver_url`.

`receiver_url` is the base BaseOS will call. The canonical value is `https://{site}/baseos`. BaseOS then uses `{receiver_url}/commands` and `{receiver_url}/health`.

The pair code expires (15 minutes in the product) and is consumed once. It is not an API token.

A successful response returns `connection_id` and `secret` once. Store the secret. Later calls sign with that secret. `status` is `healthy`, or `pending_confirm` when the site host does not match the project domain.

Schema: `schemas/pairing-request.schema.json`, `schemas/pairing-response.schema.json`.
