# Site identity

A connection belongs to one public site.

- At pair time the website sends `site_url`.
- BaseOS stores that host on the connection.
- If the receiver host and the site host differ (ignoring a leading `www.`), pairing does not mark the connection healthy.
- After pairing, `connection_id` is the stable id. Do not invent a second site id in the connector.

The website keeps its own copy of `connection_id`, `secret`, `site_url`, and `receiver_url`.
