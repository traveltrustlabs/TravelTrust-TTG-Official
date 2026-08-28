# Legacy Policy

**Upstream:** Documentation Truth Baseline · Design Lock **DL_R1** · Whitepaper PASS  
**Mainnet:** `MAINNET_DEPLOYED_PHASE1` / `TIMELOCK_CUTOVER_PENDING` · **≠** Fully Active · **≠** `TT_PRODUCTION_GO`

Historical evidence is retained. It is **not** Official V9 ACTIVE truth.

| Asset | Address | Disposition |
|-------|---------|-------------|
| Legacy Safe | `0x96491aa894658ff7946506318c49F3c76b8f40e7` | **LEGACY** · one-shot KEEP Timelock only |
| KEEP Timelock (legacy gov root) | `0x50F0B26167EC73e327D97c54C81F1c1B9eFB22f7` | **LEGACY** for V9 Official admin |
| Phase1 SoloTimelock (48h) | `0x99e43FaBA8dC773888223f70e1dfCd18bea37D7f` | **LEGACY** for Official PM/Vault after PATH_A; still 48h on-chain |
| Legacy P4Cap | `0xfB906ae34521E0BC884AB1a8D0dcf986aBD59BbF` | **LEGACY** · not V9 sale USDC sink |
| V8 TTG / PM / Governor | (see FTB historical) | **SUPERSEDED** as Official V9 root |
| Remint / `R2_FINAL` / old V9 candidates | — | **LEGACY / SUPERSEDED / DO_NOT_USE_AS_ACTIVE_TRUTH** |
| `globalStakers` 35.75% / old “83” four-leg ACTIVE | — | **EXIT / LEGACY** |

Rules:
1. Mark LEGACY / SUPERSEDED / HISTORICAL / DO_NOT_USE_AS_ACTIVE_TRUTH — do not delete evidence.
2. Do not put Legacy addresses into ACTIVE Contract Registry.
3. Safe + KEEP Timelock: allowed **only** for one-shot SettlementRouter `setFeeRouter` retarget.
4. Remint / `R2_FINAL` PASS are **LEGACY / SUPERSEDED** and do **not** cover Design Lock DL_R1 Mainnet Official ACTIVE.
