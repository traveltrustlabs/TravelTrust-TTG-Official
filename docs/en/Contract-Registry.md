# Contract Registry (table 1-01 · fifteen machines)

**Upstream:** living TravelTrust Web3 release notes (Canvas / satellite HTML) · **not** the Phase1 short table  
**Mainnet:** this roster is the living set · contracts deployed · conversion not open

Roster = latest + upgrade-in-progress + pending deploy + people keys. Old keys and retired shops: [Legacy Policy](Legacy-Policy.md) — **not** Official living roots.

| # | Name | Does | How new | On-chain? | Address |
|---|------|------|---------|-----------|---------|
| 01 | Governance token | Vote, sale, steward metering; no mint | Remint | Broadcast | `0x01dc2706c4E0F82995d63042c06873d1DC6B3AEa` |
| 02 | Governor | ~7-day holder vote, then 12h door | Remint | Broadcast · do not queue old #1 | `0xf9D9143bB632096ABeFd943D894c43C04fD16ED4` |
| 03 | 12h Timelock | Last 12h wait; anyone may execute when due | Remint | delay=43200 · do not execute old 03 | `0xafaee79259c831630E6f7Dc5B8885E0Fbe27fb5F` |
| 04 | FeeRouterV2 | Splits extracted platform fee (default 5%) | Remint | Live fee sink · allowlist executed | `0x95E794B6Ed6Ce2547b22b220761De106c5f42515` |
| 05 | ProjectPoolV2 | Sale USDC and no-seat fees land here | Remint | Broadcast | `0x55cBeD4460Ad2bCc0a9F2598af5013415B121d61` |
| 06 | PrimaryMarket | Five short windows; this five locked | Remint | Seeded · buy waits 09:00 UTC | `0xEaB632241C9c93B9012fc60a834d2D771E620130` |
| 07 | Vault | Genesis 50% TTG; unsold returns; burn via 12h | Remint | 12.5T | `0x5Ce1f7A8a9560aFf257B184F012e87B7ee2f3A6A` |
| 08 | Empty slot (not deployed) | Number kept. Live fees 11→12→13→04 | Not built | Not deployed | — |
| 09 | USDC | Circle USD; sale, deposits, 300k | This machine | Pinned | `0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48` |
| 10 | RoleStake | Steward TTG seat; 300k to #14, TTG in this machine | Remint | Allowlist executed | `0x3E7C7b2238d90dea4D31A2ee397068CB2ecF1032` |
| 11 | Escrow factory | Mints escrow on Official checkout | Remint | Traveler confirms then release | `0x61c459f3fdD61a9194D23B26acA9DDC6Df9839aB` |
| 12 | SettlementRouter | Pays principal, takes 5% to fee router | Remint | Guide does not sign payout | `0xEe34DB838cf40b1C9b2AC2248340eFc8Ea8A1C16` |
| 13 | Completion adapter | Calls fee router with country | Remint | Wired at 04 initialize | `0x4316FeC59EB5dedf66c9948E66BbBaa9d67294F0` |
| 14 | Pause key (person wallet) | Ops wallet: pause sale; 300k access. Not a smart contract. Not P4 ops spend. | Person | Same as 7% | `0xe3DE92DcB96396E75093A873C231Bb9Dd050346E` |
| 15 | Scheduler key (person wallet) | Ops wallet: schedules the 12h door. Genesis 5%. P4 ops spend (90d ≤30%) lands here. Not a smart contract. | Person | Same as 5% | `0xee05e6BcC658D3f3900Cc1CACeBE9eef8DbB40B1` |

Per-machine 20-row guide: satellite [TravelTrust-Web3-发布说明.html](https://github.com/TT-Cc19873/TravelTrust-TTG-Primary-Market/blob/main/TravelTrust-Web3-%E5%8F%91%E5%B8%83%E8%AF%B4%E6%98%8E.html) → table 1-01 → **Open**.

**11 RETIRED / HISTORICAL:** older `0xEE0BE3a8a8658E06c44539deD758Fb70A7f3C1C6` and previous live `0xcF5E02a81f10f2d6fa7BEbBb5baE3ADf658cFFFE` are parse-only for old orders. Never runtime / default / fallback / new pay. Live 11 = table above. Written production go-live has not been issued. Official API + www swapped. Owner unlocked the new-11 envelope (`MAINNET_REMINT_PENDING=false`); broadcast still closed. App install / TestFlight not cut over. Affiliate DAO `0x6fc3Be4999DE2Ad648C70e72076a66A7cB90a3c1` · Activity `0xAAc1A74d6b76405427102b602a8d7fE320f89de8` (genesis 0).
