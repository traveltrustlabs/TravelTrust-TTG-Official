# Legacy 政策

**上游：** Documentation Truth Baseline · Design Lock **DL_R1** · Whitepaper PASS  
**Mainnet：** `MAINNET_DEPLOYED_PHASE1` / `TIMELOCK_CUTOVER_PENDING` · **≠** Fully Active · **≠** `TT_PRODUCTION_GO`

历史证据保留，**不是** Official V9 ACTIVE 真值。

| Asset | Address | Disposition |
|-------|---------|-------------|
| Legacy Safe | `0x96491aa894658ff7946506318c49F3c76b8f40e7` | **LEGACY** · 仅一次性 KEEP Timelock |
| KEEP Timelock（旧治理根） | `0x50F0B26167EC73e327D97c54C81F1c1B9eFB22f7` | **LEGACY** · 非 V9 Official admin |
| Phase1 SoloTimelock（48h） | `0x99e43FaBA8dC773888223f70e1dfCd18bea37D7f` | **LEGACY** · Official PM/Vault 已切 NEW 12h 之后；链上仍 48h |
| Legacy P4Cap | `0xfB906ae34521E0BC884AB1a8D0dcf986aBD59BbF` | **LEGACY** · 非 V9 公售 USDC sink |
| Phase1 ProjectPool | `0x7B21b421981A3B61cc08c8E22D4fd690E457Df37` | **LEGACY** · 活收款口是表 1-01 项目美元池 `0x65714…` |
| Phase1 CountryFeeRouter | `0x5afD2e0C8b9fa4eecfde4bf582d3B282D28F4970` | **LEGACY** · 活分账是 FeeRouterV2 `0x2F3F41…` |
| Phase1 Governor | `0xA0DfC4C5C544488AfEfE696AfB8e5823911e5A9c` | **LEGACY** · 活投票机 `0xD4b616…` |
| Phase1 RoleStake | `0xf6A1Fb4435E463117a666818611F49D03F91E7A7` | **LEGACY** · 活席位 `0xa983…` |
| V8 TTG / PM / Governor |（见 FTB 历史） | **SUPERSEDED** as Official V9 root |
| Remint / `R2_FINAL` / 旧 V9 candidates | — | **LEGACY / SUPERSEDED / DO_NOT_USE_AS_ACTIVE_TRUTH** |
| `globalStakers` 35.75% / 旧「83」四腿 ACTIVE | — | **EXIT / LEGACY** |

规则：
1. 仅标记 LEGACY / SUPERSEDED / HISTORICAL / DO_NOT_USE_AS_ACTIVE_TRUTH — 不删除证据。
2. Legacy 地址不得进入 ACTIVE 合约登记。
3. Safe + KEEP Timelock：**仅**允许一次性 SettlementRouter `setFeeRouter` 切针。
4. Remint / R2_FINAL PASS **不覆盖** Design Lock DL_R1 Mainnet Official ACTIVE。
