# 治理

**事实：** TravelTrust Web3 发布说明 **V2** 表 1-01  
**Mainnet：** 合约已部署 · 兑换尚未开放 · **≠** Fully Active · **≠** `TT_PRODUCTION_GO`

```text
02 投票机 → 03 十二小时门（delay 43200）
             15 预约人 admin = 0xee05e6BcC658D3f3900Cc1CACeBE9eef8DbB40B1
```

- **无 Safe** 作为 V9 Official Timelock admin
- 价格/批次/费率/payout 映射变更：仅治理路径
- Governance Burn：02 → 03 → 授权 burner（01 上销毁钥仍钉死）
- **02 投票机**（持币人约 7 天投票；通过后再进 12 小时门）：`0x69fF62475C3ed36B3B8627BfEC980b3047B3bf42`
- **03 十二小时门**（最后 12 小时等待门；门不是仓）：`0x2Cb9f0FD770B50931f0a4cd463113bBA39331acb`
- **15 预约人**（12 小时门预约人；5% 营销钥；不是国库）：`0xee05e6BcC658D3f3900Cc1CACeBE9eef8DbB40B1`
- Phase1 投票机 `0xD4b6162CB344af2C44689717edDFEe21e9082205` 与更早 `0xA0DfC4C5C544488AfEfE696AfB8e5823911e5A9c` = **LEGACY**
- Phase1 12 小时门 `0xF61880fe9943BBc624F487782E2fB35d8Ae50E3A` = **LEGACY**（不是 V2 活门）
- Phase1 48h SoloTimelock `0x99e43FaBA8dC773888223f70e1dfCd18bea37D7f` = **LEGACY**
- Phase1 预约人 `0xe1e732EfBf9B010a9204054467256d3d93f3CdD4` = **LEGACY**
- Sepolia 排练也是 **12h**，但是**另一条链/另一地址**（[Sepolia](../deployments/sepolia.md)）— **勿混用地址**。
