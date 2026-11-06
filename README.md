# connect-spec

BaseOS Connect Protocol 2.1. This repository is the contract. It is not an API server.

- Human guide: [`protocol/2.1/overview.md`](protocol/2.1/overview.md)
- Machine contract: [`connect-protocol.json`](connect-protocol.json)
- OpenAPI of the live Core routes: [`openapi/openapi.yaml`](openapi/openapi.yaml)

Production calls go to `https://baseos.net/api/v1/connect`. Customer websites expose `https://{site}/baseos`.

Laravel package: `baseos/connect-laravel`. Node SDK: `@baseos/connect-node` (npm organization `baseos`). CLI: `baseos-connect`, shipped inside the Node package.
