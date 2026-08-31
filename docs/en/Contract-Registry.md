# Contract Registry (table 1-01 · fifteen machines)

**Upstream:** living TravelTrust Web3 release notes (Canvas / satellite HTML) · **not** the Phase1 short table  
**Mainnet:** this roster is the living set · **≠** Fully Active · **≠** `TT_PRODUCTION_GO`

Roster = latest + upgrade-in-progress + pending deploy + people keys. Old keys and retired shops: [Legacy Policy](Legacy-Policy.md) — **not** Official living roots.

| # | Name | Does | How new | On-chain? | Address |
|---|------|------|---------|-----------|---------|
| 01 | Governance token | Vote, sale, steward metering; no mint | This machine | Doorplate live | `0xD5c1Ef9ec730F93e324A1966bD414a7f5ebc41c9` |
| 02 | Governor | ~7-day holder vote, then 12h door | This machine | Doorplate live | `0xD4b6162CB344af2C44689717edDFEe21e9082205` |
| 03 | 12h Timelock | Last 12h wait; anyone may execute when due | This machine | Door live · keys handed | `0xF61880fe9943BBc624F487782E2fB35d8Ae50E3A` |
| 04 | FeeRouterV2 | Splits extracted platform fee (default 5%) | This machine | Rules live · not called yet | `0x2F3F4120d9d10b52f7FF762aC7E8f563454A9704` |
| 05 | ProjectPoolV2 | Sale USDC and no-seat fees land here | This machine | Treasury pointer cut | `0x65714bbF2f3B8bB7E4c71F5D51C0bbe6869dAB68` |
| 06 | PrimaryMarket | Five short windows; this five locked | Upgradeable · five locked | Windows not open | `0xc714E2567982ea92d5f3C5b66ab65532Cfc5f09b` |
| 07 | Vault | Genesis 50% TTG; unsold returns; burn via 12h | This machine | Admin 12h · no burn yet | `0xe87378e49Ead2E1a422B8cae118d3C905Ee45B6C` |
| 08 | Live trip fee contract | Settlement router sends the platform fee here | This machine | Live fee sink | `0xa20a2987c688b8CAB21E1f54B6Ad103926B4082b` |
| 09 | USDC | Circle USD; sale, deposits, 300k | This machine | Pinned | `0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48` |
| 10 | RoleStake | Steward TTG seat; 300k to #14, TTG in this machine | Swap impl | Address final · impl old | `0xa9839Ef49e1Cc6095b41764DCf81346250A469F8` |
| 11 | Escrow factory | Mints escrow on Official checkout | This machine | Pointer cut · key 12h | `0xEE0BE3a8a8658E06c44539deD758Fb70A7f3C1C6` |
| 12 | SettlementRouter | Pays principal, takes 5% to fee router | This machine | Knows V2 · next pointer queued | `0xe5C3ED16741Eb195fAE11b0C1449A79DD675B372` |
| 13 | Completion adapter | Calls fee router with country; does not change KEEP | Doorplate · not wired | Queued for 12h | `0x94e2be00877c4519805408e10e16e33625863c74` |
| 14 | Pause key (person wallet) | Ops wallet: pause sale; default payee and 300k access. Not a smart contract. | Person | Three jobs | `0xF34804AA66bAeE02F3aF1C540B9997C7F46b2736` |
| 15 | Scheduler key (person wallet) | Ops wallet: schedules the 12h door. Not treasury, not a smart contract. | Person | Schedule key | `0xe1e732EfBf9B010a9204054467256d3d93f3CdD4` |

Per-machine 20-row guide: satellite [TravelTrust-Web3-发布说明.html](https://github.com/TT-Cc19873/TravelTrust-TTG-Primary-Market/blob/main/TravelTrust-Web3-%E5%8F%91%E5%B8%83%E8%AF%B4%E6%98%8E.html) → table 1-01 → **Open**.
