# Signature

HMAC-SHA256. The key is the full secret string BaseOS issued, including the `whsec_` prefix. Do not base64-decode it.

Signed string: `{webhook-id}.{webhook-timestamp}.{raw body}`

Header: `webhook-signature: v1,<base64>`

Also send `webhook-id`, `webhook-timestamp`, `baseos-connection`, and `baseos-protocol` (`2.1`).

Receivers reject timestamps more than 300 seconds from their clock. During secret rotation the header may carry two `v1,` signatures; either match is enough.

Laravel `BaseOS\Connect\Signing\Signer` and Node `Signer` implement this same rule.
