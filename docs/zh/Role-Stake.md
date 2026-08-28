# Role Stake

**上游：** Documentation Truth Baseline · Design Lock **DL_R1** · Whitepaper PASS（Stake Layer Split · Guide Per-Order Bond）  
**Mainnet：** `MAINNET_DEPLOYED_PHASE1` / `TIMELOCK_CUTOVER_PENDING` · **≠** Fully Active · **≠** `TT_PRODUCTION_GO`

| 角色 | 状态 | 门槛 / 履约 |
|------|------|-------------|
| Region Steward | **ACTIVE** | TTG Seat：`live totalSupply() × country_bps / 10000` |
| Merchant | **`NOT_REQUIRED` / `DISABLED`** | **不质押 TTG** · 履约押规则 **独立未确认**（不继承 Guide） |
| Guide | **`NOT_REQUIRED` / `DISABLED`** | **不质押 TTG** · 履约 = **逐订单 USDC Performance Bond**（确认订单后锁入 · 完成全额返还 · 仅 Dispute 裁决后可罚没） |

**禁止：** 把 81 Identity 长期身份质押写成订单履约押。实现审计：**`NEW_ORDER_BOND_MODULE_REQUIRED`**。

初始 Steward bps：CN/US 400 · FR/ES 450 · JP/TH 250 · SG/KR 200 · AU/AE 150。  
地址：`0xf6A1Fb4435E463117a666818611F49D03F91E7A7` · `DEPLOYED_PENDING_CUTOVER`
