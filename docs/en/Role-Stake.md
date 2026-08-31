# Role Stake

**Upstream:** Documentation Truth Baseline · Design Lock **DL_R1** · Whitepaper PASS (Stake Layer Split · Guide Per-Order Bond)  
**Mainnet:** `MAINNET_DEPLOYED_PHASE1` / `TIMELOCK_CUTOVER_PENDING` · **≠** Fully Active · **≠** `TT_PRODUCTION_GO`

| Role | Status | Threshold / performance |
|------|--------|-------------------------|
| Region Steward | **ACTIVE** | TTG Seat: `live totalSupply() × country_bps / 10000` |
| Merchant | **`NOT_REQUIRED` / `DISABLED`** | **No TTG stake** · bond rules **independent / unconfirmed** (do not inherit Guide) |
| Guide | **`NOT_REQUIRED` / `DISABLED`** | **No TTG stake** · performance = **per-order USDC Performance Bond** (lock after confirm, before fulfill; full refund on success; slash only after Dispute) |

**Forbidden:** treating 81 long-lived Identity stake as the order performance bond. Implementation audit: **`NEW_ORDER_BOND_MODULE_REQUIRED`**.

Initial Steward bps: CN/US 400 · FR/ES 450 · JP/TH 250 · SG/KR 200 · AU/AE 150.  
Living address (table 1-01 · **10 RoleStake**): does = **steward TTG seat; 300k to #14, TTG locked in this machine**. `0xa9839Ef49e1Cc6095b41764DCf81346250A469F8`. Impl is still old; 12h `upgradeTo` (SeatLock) before claiming apply/exit is live on mainnet. Phase1 `0xf6A1Fb…` = **LEGACY**.
