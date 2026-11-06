# Synchronisation

BaseOS pushes a command envelope to `POST {receiver_url}/commands`. The body is `schemas/command-envelope.schema.json`.

Idempotency is per connection, command type, and `idempotency_key`. `post.find` may reuse the key from a previous `post.upsert` to ask whether that write landed. The receiver must not replay the upsert result as the find result.

`post.validate` is never cached.

The website reports local edits with `POST /api/v1/connect/events` (`post.changed`, `post.deleted`), signed the same way.

`php artisan baseos:sync` and `npx baseos-connect sync` send `hello` plus the site schema. They do not invent a second sync endpoint.
