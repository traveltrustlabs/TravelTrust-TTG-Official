# Role Stake

**Upstream:** Documentation Truth Baseline · Design Lock **DL_R1** · Whitepaper PASS (Stake Layer Split · Guide Per-Order Bond)  
**Mainnet:** `MAINNET_DEPLOYED_PHASE1` / `TIMELOCK_CUTOVER_PENDING` · **≠** Fully Active

| Role | Status | Threshold / performance |
|------|--------|-------------------------|
| Region Steward | **ACTIVE** | TTG Seat: `live totalSupply() × country_bps / 10000` |
| Merchant | **`NOT_REQUIRED` / `DISABLED`** | **No TTG stake** · bond rules **independent / unconfirmed** (do not inherit Guide) |
| Guide | **`NOT_REQUIRED` / `DISABLED`** | **No TTG stake** · performance = **per-order USDC Performance Bond** (lock after confirm, before fulfill; full refund on success; slash only after Dispute) |

**Forbidden:** treating 81 long-lived Identity stake as the order performance bond. Implementation audit: **`NEW_ORDER_BOND_MODULE_REQUIRED`**.

Initial Steward bps: CN/US 400 · FR/ES 450 · JP/TH 250 · SG/KR 200 · AU/AE 150.  
Living address (table 1-01 · **10 RoleStake**): does = **steward TTG seat; 300k to new #14, TTG locked in this machine**. `0x3E7C7b2238d90dea4D31A2ee397068CB2ecF1032`. 03 allowlist executed. Old `0xa9839Ef4…` RETIRED. Phase1 `0xf6A1Fb…` = **LEGACY**.
