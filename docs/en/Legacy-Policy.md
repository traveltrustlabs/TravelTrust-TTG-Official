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
| Phase1 ProjectPool | `0x7B21b421981A3B61cc08c8E22D4fd690E457Df37` | **LEGACY** · living sink is table 1-01 pool `0x65714…` |
| Phase1 CountryFeeRouter | `0x5afD2e0C8b9fa4eecfde4bf582d3B282D28F4970` | **LEGACY** · living splitter is FeeRouterV2 `0x2F3F41…` |
| Phase1 Governor | `0xA0DfC4C5C544488AfEfE696AfB8e5823911e5A9c` | **LEGACY** · living Governor `0xD4b616…` |
| Phase1 RoleStake | `0xf6A1Fb4435E463117a666818611F49D03F91E7A7` | **LEGACY** · living seat `0xa983…` |
| V8 TTG / PM / Governor | (see FTB historical) | **SUPERSEDED** as Official V9 root |
| Remint / `R2_FINAL` / old V9 candidates | — | **LEGACY / SUPERSEDED / DO_NOT_USE_AS_ACTIVE_TRUTH** |
| `globalStakers` 35.75% / old “83” four-leg ACTIVE | — | **EXIT / LEGACY** |

Rules:
1. Mark LEGACY / SUPERSEDED / HISTORICAL / DO_NOT_USE_AS_ACTIVE_TRUTH — do not delete evidence.
2. Do not put Legacy addresses into ACTIVE Contract Registry.
3. Safe + KEEP Timelock: allowed **only** for one-shot SettlementRouter `setFeeRouter` retarget.
4. Remint / `R2_FINAL` PASS are **LEGACY / SUPERSEDED** and do **not** cover Design Lock DL_R1 Mainnet Official ACTIVE.
