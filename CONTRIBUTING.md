# Contributing (public Web3 surface)

**Upstream truth:** Documentation Truth Baseline + Design Lock DL_R1.  
**Do not** propose ACTIVE narratives that revive `globalStakers`, R2_FINAL, Remint, Safe-as-V9-admin, or Legacy P4Cap sale sinks.

## Allowed

- Doc clarifications that preserve Mainnet status `DEPLOYED_PENDING_CUTOVER` / `TIMELOCK_CUTOVER_PENDING`
- Bug reports via [SECURITY.md](SECURITY.md)
- PRs that sync public docs to Baseline after Owner-approved Reality changes

## Forbidden without Owner written gate

- Mutating DL_R1 Solidity / bytecode / Phase1 addresses / live params
- Claiming `MAINNET_FULLY_ACTIVE` or flipping `TT_PRODUCTION_GO`
- Publishing secrets, `.env`, private keys, or internal evidence packs
- Auto push / publicize / Official www or Production `/meta`·Indexer cutover

Implementation changes happen in the private monorepo — not in this public docs repository.
