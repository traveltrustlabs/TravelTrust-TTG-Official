# 治理

**上游：** Documentation Truth Baseline · Design Lock **DL_R1** · Whitepaper PASS  
**Mainnet：** `MAINNET_DEPLOYED_PHASE1` / `TIMELOCK_CUTOVER_PENDING` · **≠** Fully Active · **≠** `TT_PRODUCTION_GO`

```text
Governor → SoloTimelock（Official PM/Vault 延迟 **12h**）
             admin = Marketing Norm 0xe1e732…
```

- **无 Safe** 作为 V9 Official Timelock admin
- 价格/批次/费率/payout 映射变更：仅治理路径
- Governance Burn：Governor → SoloTimelock → 授权 burner
- Phase1 Governor：`0xA0DfC4C5C544488AfEfE696AfB8e5823911e5A9c`
- Official PM/Vault 延迟（PATH_A 之后）：NEW SoloTimelock **12h** `0xF61880fe9943BBc624F487782E2fB35d8Ae50E3A`
- Phase1 OLD SoloTimelock **48h** `0x99e43FaBA8dC773888223f70e1dfCd18bea37D7f` = **LEGACY**（链上仍是 48h，不是活 Official 延迟）
- Sepolia V9 外围排练也是 **12h**，但是**另一条链/另一地址**（[Sepolia 部署](../deployments/sepolia.md)）— **勿混用地址**。
