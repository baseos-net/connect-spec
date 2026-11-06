# BaseOS Connect Protocol 2.1

One contract for every connector. BaseOS Core is the only backend. Laravel and Node.js are adapters: they pair, sign, and accept the same commands.

Machine-readable source: [`connect-protocol.json`](../connect-protocol.json).

| Piece | Rule |
|---|---|
| API | `https://baseos.net` + `/api/v1/connect` |
| Receiver | `https://{site}/baseos` — `POST /commands`, `GET /health` |
| Pairing | One-time code. The response secret is the long-lived credential |
| Signature | HMAC-SHA256 over `{webhook-id}.{webhook-timestamp}.{raw body}` |
| Site | `site_url` at pair time, then `connection_id` |
| Tenant | Optional id stored on that connection |
| Capabilities | The `commands` list in `connect-protocol.json` |
| Compatibility | `2.1` preferred, `2.0` still accepted |

`POST https://baseos.net/api/v1/connect/pair` is not this API. On 2026-11-06 that path belonged to another GET route.
