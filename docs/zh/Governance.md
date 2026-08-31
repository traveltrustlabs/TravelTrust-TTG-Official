# 治理

**上游：** Documentation Truth Baseline · Design Lock **DL_R1** · Whitepaper PASS  
**Mainnet：** `MAINNET_DEPLOYED_PHASE1` / `TIMELOCK_CUTOVER_PENDING` · **≠** Fully Active · **≠** `TT_PRODUCTION_GO`

```text
02 投票机 → 03 十二小时门（Official 一级市场/Vault 延迟 **12h**）
             15 预约人 admin = 0xe1e732…
```

- **无 Safe** 作为 V9 Official Timelock admin
- 价格/批次/费率/payout 映射变更：仅治理路径
- Governance Burn：02 → 03 → 授权 burner（01 上销毁钥仍钉死，本批不改 01）
- **02 投票机**（持币人约 7 天投票；通过后再进 12 小时门）：`0xD4b6162CB344af2C44689717edDFEe21e9082205`
- Phase1 Governor `0xA0DfC4C5C544488AfEfE696AfB8e5823911e5A9c` = **LEGACY**
- **03 十二小时门**（最后 12 小时等待门；到期谁都能按执行）：`0xF61880fe9943BBc624F487782E2fB35d8Ae50E3A`
- **15 预约人**（12 小时门预约人；不是国库）：`0xe1e732EfBf9B010a9204054467256d3d93f3CdD4`
- Phase1 OLD SoloTimelock **48h** `0x99e43FaBA8dC773888223f70e1dfCd18bea37D7f` = **LEGACY**（链上仍是 48h，不是活 Official 延迟）
- Sepolia V9 外围排练也是 **12h**，但是**另一条链/另一地址**（[Sepolia 部署](../deployments/sepolia.md)）— **勿混用地址**。
