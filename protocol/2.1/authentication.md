# Authentication

After pairing, the pair code is useless. The credential is:

- `connection_id` in the `baseos-connection` header
- `secret` as the HMAC key (see signature.md)

`/pair` is the only unsigned call. `hello`, `commands`, `events`, and content reads require a valid signature.

Disconnecting on the website deletes the stored secret so the website stops accepting commands. Revoke the same connection in BaseOS so the credential is not treated as live there. There is no second revoke API on the receiver.
