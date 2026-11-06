# Contract checks

`connect-protocol.json` is the list both SDKs must match.

- `connect-laravel` test: `tests/ProtocolContractTest.php` reads `protocol/connect-protocol.json` inside that package.
- `connect-node` test: `test/protocol.test.ts` reads `protocol/connect-protocol.json` inside that package.

When this repository changes the command list, origin, or path, copy `connect-protocol.json` into both packages before tagging them. The packages do not depend on this repo at runtime.
