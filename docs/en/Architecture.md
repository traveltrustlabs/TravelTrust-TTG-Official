# Architecture

**Upstream:** Documentation Truth Baseline · `V9_DOCUMENTATION_FULL_CONVERGENCE_PASS` · `TTG_V9_MAINNET_EDITION_WHITEPAPER_PASS` · Design Lock **DL_R1**  
**Mainnet:** `MAINNET_DEPLOYED_PHASE1` / `TIMELOCK_CUTOVER_PENDING` · **≠** Fully Active · **≠** `TT_PRODUCTION_GO`

TravelTrust Web3 Mainnet Edition uses a **NEW / KEEP / LEGACY** split:

| Class | Meaning |
|-------|---------|
| **NEW** | V9 Official token, SoloTimelock, Governor, Vault, Market, ProjectPool, CountryFeeRouter, RoleStake |
| **KEEP** | EscrowFactoryV2Wired + SettlementRouter + USDC Money Path (user principal) |
| **LEGACY** | Safe / old Timelock / P4Cap / V8 / Remint / R2_FINAL — **not** ACTIVE Contract Registry |

```text
Order(+ISO country) → KEEP Escrow / Settlement
  → fee 5% → NEW CountryFeeRouter
       ├─ Active steward → 45% payout wallet / 55% NEW ProjectPool
       └─ none → 100% NEW ProjectPool
Primary sale USDC → NEW ProjectPool (never Legacy P4Cap)
Governor → SoloTimelock 12h (Official PM/Vault) → periphery ops / Governance Burn
  (Phase1 OLD 48h SoloTimelock = LEGACY)
```

Token monetary rules are **immutable NO-MINT**. Periphery may upgrade via governance **without** minting beyond genesis.
