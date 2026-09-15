# Architecture

**Upstream:** Documentation Truth Baseline · `V9_DOCUMENTATION_FULL_CONVERGENCE_PASS` · `TTG_V9_MAINNET_EDITION_WHITEPAPER_PASS` · Design Lock **DL_R1**  
**Mainnet:** contracts deployed · conversion not open · **≠** Fully Active · **≠** `TT_PRODUCTION_GO`

The living Web3 roster is **only table 1-01** from TravelTrust Web3 发布说明 **V2**. Addresses: [Contract Registry](Contract-Registry.md).

| Class | Meaning |
|-------|---------|
| **Table 1-01** | Fifteen living machines |
| **08** | **Not deployed** this edition |
| **LEGACY** | Lost-key / Phase1 / V8 / Remint — [Legacy Policy](Legacy-Policy.md) |

| # | Name | Does |
|---|------|------|
| 01 | Governance token | Vote, sale, steward metering; no mint |
| 02 | Governor | ~7-day holder vote, then 12h door |
| 03 | 12h Timelock | Last 12h wait; the door is not a treasury |
| 04 | Fee router | Splits extracted platform fee (default 5%) |
| 05 | Project pool | Sale USDC and no-seat fees land here |
| 06 | Primary market | Five short windows; this five locked |
| 07 | Vault | Genesis 50% TTG (12.5T) |
| 08 | (reserved) | **Not deployed** |
| 09 | USDC | Circle USD; sale, deposits, access fee |
| 10 | RoleStake | Steward TTG seat; 300k to #14 |
| 11 | Escrow factory | Mints escrow on checkout |
| 12 | Settlement router | Pays principal; fee to #13 → #04 |
| 13 | Completion adapter | Calls fee router with country |
| 14 | Pause | Pause sale; 7% key; 300k access-fee payee |
| 15 | Scheduler | 12h admin; 5% key; pool ops payee |

```text
Order(+ISO country) → #11 factory → #12 settlement → #13 adapter → #04 fee router
  → 5% fee
       ├─ Active steward → 45% payout wallet / 55% #05
       └─ none → 100% #05
Sale USDC (#09) → #06 counter → dollars to #05; TTG from #07
#02 Governor → #03 12h door → periphery ops / Governance Burn
```

Token monetary rules are **immutable NO-MINT**. Periphery may upgrade via governance **without** minting beyond genesis.
