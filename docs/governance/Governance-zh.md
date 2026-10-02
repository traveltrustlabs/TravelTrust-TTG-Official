# 治理

**上游：** TravelTrust Web3 发布说明 **表 1-01** · **≠** Fully Active · **≠** `TT_PRODUCTION_GO`

```text
02 投票机 → 03 十二小时门（Official 延迟 **12h**）
             15 预约人 admin = 0xee05e6BcC658D3f3900Cc1CACeBE9eef8DbB40B1
```

- **无 Safe** 作为 V9 Official Timelock admin
- 价格/批次/费率/payout 映射变更：仅治理路径
- Governance Burn：02 → 03 → 授权 burner（01 上销毁钥仍钉死，本批不改 01）
- **02 投票机**：`0xf9D9143bB632096ABeFd943D894c43C04fD16ED4`（旧 `0xD4b6162C…` RETIRED · 旧 #1 禁止 queue）
- Phase1 Governor `0xA0DfC4C5C544488AfEfE696AfB8e5823911e5A9c` = **LEGACY**
- **03 十二小时门**：`0xafaee79259c831630E6f7Dc5B8885E0Fbe27fb5F`（delay=43200 · **禁止 execute 旧 03** `0xF61880fe…`）
- **15 预约人**（部署/12h 预约 · 创世 5% · 项目池运营取款）：`0xee05e6BcC658D3f3900Cc1CACeBE9eef8DbB40B1`（旧 EOA `0xe1e732…` 不是此角色）
- Phase1 OLD SoloTimelock **48h** `0x99e43FaBA8dC773888223f70e1dfCd18bea37D7f` = **LEGACY**
- Sepolia 是另一条链 — **勿混用地址**。
