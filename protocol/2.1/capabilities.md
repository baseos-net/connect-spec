# Capabilities

Protocol 2.1 baseline, implemented by BaseOS Core and by both SDKs:

`post.upsert`, `post.set_state`, `post.fetch`, `post.find`, `post.validate`, `site.health`, `site.schema`, `site.verify`.

`hello` and `site.health` announce a `features` list. BaseOS only sends a command the receiver listed. `post.validate` checks a post and writes nothing.

A connector must not advertise a feature its repository does not implement.
