# Tenant identity

One codebase can serve many websites. Each pairing stores an optional tenant id chosen by that codebase (`--tenant` on the CLI and on `php artisan baseos:pair`).

The tenant id is an opaque string owned by the website. BaseOS does not assign it. Commands for that connection run inside the tenant scope the connector registered. Two tenants on one codebase are two connections, each with its own secret.
