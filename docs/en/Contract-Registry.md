# Contract Registry (table 1-01 · fifteen machines)

**Upstream:** living TravelTrust Web3 release notes (Canvas / satellite HTML) · **not** the Phase1 short table  
**Mainnet:** this roster is the living set · contracts deployed · conversion not open

Roster = latest + upgrade-in-progress + pending deploy + people keys. Old keys and retired shops: [Legacy Policy](Legacy-Policy.md) — **not** Official living roots.

| # | Name | Does | How new | On-chain? | Address |
|---|------|------|---------|-----------|---------|
| 01 | Governance token | Vote, sale, steward metering; no mint | V2 | Broadcast | `0xd9965802ff0A9DAB5d0E13392dA797cd6D13ee51` |
| 02 | Governor | ~7-day holder vote, then 12h door | V2 | Broadcast · do not queue old #1 | `0x69fF62475C3ed36B3B8627BfEC980b3047B3bf42` |
| 03 | 12h Timelock | Last 12h wait; anyone may execute when due | V2 | delay=43200 · do not execute old 03 | `0x2Cb9f0FD770B50931f0a4cd463113bBA39331acb` |
| 04 | FeeRouterV2 | Splits extracted platform fee (default 5%) | V2 | Live fee sink · allowlist executed | `0x4aC011Dd589756fa1C8161733f645660D14A7E79` |
| 05 | ProjectPoolV2 | Sale USDC and no-seat fees land here | V2 | Broadcast | `0xD49F33c1f1d806500407550f8e92b0d1b3d725d9` |
| 06 | PrimaryMarket | Five short windows; this five locked | V2 | Seeded · buy waits 09:00 UTC | `0xaB1D74A62e3fBB1c140a9Dfa9bB5b7Fe3F8C7e46` |
| 07 | Vault | Genesis 50% TTG; unsold returns; burn via 12h | V2 | 12.5T | `0x1c9dBa15eBFB31Dd4BDa608b7b003B3ba4a61287` |
| 08 | Empty slot (not deployed) | Number kept. Live fees 11→12→13→04 | Not built | Not deployed | — |
| 09 | USDC | Circle USD; sale, deposits, 300k | This machine | Pinned | `0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48` |
| 10 | RoleStake | Steward TTG seat; 300k to #14, TTG in this machine | V2 | Allowlist executed | `0x131fa67a38563c99Aa65B4470d568d8aC738D77b` |
| 11 | Escrow factory | Mints escrow on Official checkout | V2 | Traveler confirms then release | `0x34d5E7eCe5c1638D6F078F0B461277EcDf64bf29` |
| 12 | SettlementRouter | Pays principal, takes 5% to fee router | V2 | Guide does not sign payout | `0x70ea026ce66C884E89b90473AcF5f2780dAE1b47` |
| 13 | Completion adapter | Calls fee router with country | V2 | Wired at 04 initialize | `0x004b6458085aaCC55dedAB52E4B004b69c832b75` |
| 14 | Pause key (person wallet) | Ops wallet: pause sale; 300k access. Not a smart contract. Not P4 ops spend. | Person | Same as 7% | `0xe3DE92DcB96396E75093A873C231Bb9Dd050346E` |
| 15 | Scheduler key (person wallet) | Ops wallet: schedules the 12h door. Genesis 5%. P4 ops spend (90d ≤30%) lands here. Not a smart contract. | Person | Same as 5% | `0xee05e6BcC658D3f3900Cc1CACeBE9eef8DbB40B1` |

Per-machine 20-row guide: satellite [TravelTrust-Web3-发布说明.html](https://github.com/TT-Cc19873/TravelTrust-TTG-Primary-Market/blob/main/TravelTrust-Web3-%E5%8F%91%E5%B8%83%E8%AF%B4%E6%98%8E.html) → table 1-01 → **Open**.

**11 RETIRED / HISTORICAL:** older `0xEE0BE3a8a8658E06c44539deD758Fb70A7f3C1C6` and previous live `0xcF5E02a81f10f2d6fa7BEbBb5baE3ADf658cFFFE` are parse-only for old orders. Never runtime / default / fallback / new pay. Live 11 = table above. Written production go-live has not been issued. Official API + www swapped. The new-11 envelope is unlocked; on-chain broadcast remains closed. App install / TestFlight not cut over. Affiliate DAO `0x063174C62A2878eB8E6c033363b8f1bA1aE9cE3b` · Activity `0xAAc1A74d6b76405427102b602a8d7fE320f89de8` (genesis 0).
