# Errors

| Code | When |
|---|---|
| `connect.pair_invalid` | Pair code, auth code, or host check failed. HTTP 422 |
| `command.unsupported` | Receiver does not implement that command. HTTP 404 |
| `command.expired` | `expires_at` has passed. BaseOS issues a new command with the same idempotency key |
| signature failure | Missing, skewed, or wrong HMAC. The receiver does not run the command |

Validation of a post uses `post.validate` issues (`code`, `path`, `message`, `blocking`). Those are content problems, not transport errors.
