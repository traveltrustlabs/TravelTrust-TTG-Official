# Role Stake

**上游：** Documentation Truth Baseline · Design Lock **DL_R1** · Whitepaper PASS（Stake Layer Split · Guide Per-Order Bond）  
**Mainnet：** `MAINNET_DEPLOYED_PHASE1` / `TIMELOCK_CUTOVER_PENDING` · **≠** Fully Active

| 角色 | 状态 | 门槛 / 履约 |
|------|------|-------------|
| Region Steward | **ACTIVE** | TTG Seat：`live totalSupply() × country_bps / 10000` |
| Merchant | **`NOT_REQUIRED` / `DISABLED`** | **不质押 TTG** · 履约押规则 **独立未确认**（不继承 Guide） |
| Guide | **`NOT_REQUIRED` / `DISABLED`** | **不质押 TTG** · 履约 = **逐订单 USDC Performance Bond**（确认订单后锁入 · 完成全额返还 · 仅 Dispute 裁决后可罚没） |

**禁止：** 把 81 Identity 长期身份质押写成订单履约押。实现审计：**`NEW_ORDER_BOND_MODULE_REQUIRED`**。

初始 Steward bps：CN/US 400 · FR/ES 450 · JP/TH 250 · SG/KR 200 · AU/AE 150。  
活地址（表 1-01 · **10 主理人席位**）：干什么 = **主理人用 TTG 占席；30 万打新 14、币锁本台**。`0x3E7C7b2238d90dea4D31A2ee397068CB2ecF1032`。03 白名单已 execute。旧 `0xa9839Ef4…` RETIRED。Phase1 `0xf6A1Fb…` = **LEGACY**。
