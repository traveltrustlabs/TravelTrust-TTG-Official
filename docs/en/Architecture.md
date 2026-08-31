# Architecture

**Upstream:** Documentation Truth Baseline · `V9_DOCUMENTATION_FULL_CONVERGENCE_PASS` · `TTG_V9_MAINNET_EDITION_WHITEPAPER_PASS` · Design Lock **DL_R1**  
**Mainnet:** `MAINNET_DEPLOYED_PHASE1` / `TIMELOCK_CUTOVER_PENDING` · **≠** Fully Active · **≠** `TT_PRODUCTION_GO`

The living Web3 roster is **only table 1-01 · fifteen machines** (jobs locked with the Canvas / HTML dashboard). **KEEP** means #11 factory and #12 SettlementRouter **keep this doorplate** — they are still in table 1-01, not LEGACY.

| Class | Meaning |
|-------|---------|
| **Table 1-01** | Fifteen living machines (jobs below) |
| **KEEP** | #11 / #12 doorplate unchanged (trip principal) |
| **LEGACY** | Safe / old 48h Timelock / P4Cap / Phase1 old pool·router·Governor·stake / V8 / Remint — **not** table 1-01 |

| # | Name | Does |
|---|------|------|
| 01 | Governance token | Vote, sale, steward metering; no mint |
| 02 | Governor | ~7-day holder vote, then 12h door |
| 03 | 12h Timelock | Last 12h wait; anyone may execute when due |
| 04 | FeeRouterV2 | Splits extracted platform fee (default 5%) |
| 05 | ProjectPoolV2 | Sale USDC and no-seat fees land here |
| 06 | PrimaryMarket | Five short windows; this five locked |
| 07 | Vault | Genesis 50% TTG; unsold returns; burn via 12h |
| 08 | Next fee router | Next splitter; asks seat; stop-on-exit (pointer not cut) |
| 09 | USDC | Circle USD; sale, deposits, access fee |
| 10 | RoleStake | Steward TTG seat; 300k to #14, TTG in this machine |
| 11 | Escrow factory | Mints escrow on Official checkout |
| 12 | SettlementRouter | Pays principal, takes 5% to fee router |
| 13 | Completion adapter | Calls fee router with country; does not change KEEP |
| 14 | Pause | Pause sale; default wage and 300k payee |
| 15 | Scheduler | 12h admin; not treasury |

```text
Order(+ISO country) → #11 factory / #12 SettlementRouter
  → fee 5% → #04 FeeRouterV2
       ├─ Active steward → 45% payout wallet / 55% #05 ProjectPoolV2
       └─ none → 100% #05
Sale USDC (#09) → #06 counter → dollars to #05; TTG from #07
#02 Governor → #03 12h door → periphery ops / Governance Burn
  (Phase1 OLD 48h SoloTimelock = LEGACY)
```

Token monetary rules are **immutable NO-MINT**. Periphery may upgrade via governance **without** minting beyond genesis.
