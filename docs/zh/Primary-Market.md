# 一级市场

**上游：** Documentation Truth Baseline · Design Lock **DL_R1** · Whitepaper PASS  
**Mainnet：** 公售时间表已 pin 为 `V9_SHORT_WINDOW_FIVE_ROUND`（Timelock execute 2026-08-26）· 兑换窗口 **尚未对公众开放** · **≠** Fully Active · **≠** `TT_PRODUCTION_GO`

NEW Batch Primary Market + PublicSaleVault 执行 Norm 五轮短窗口（官网发布说明名称：创始校准 / 社区早鸟 / 建设者轮 / 公开轮 / 最终公开轮；合计约占 25T 的 **3.905%**）：

| 轮次 | 名称 | Cap（TTG） | 约 USDC / 1 TTG | UTC 窗口 |
|------|------|------------|-----------------|----------|
| ① | 创始校准 | 1.25B（约 12.5 亿） | $0.000001 | 2026-10-15 → 2026-10-22（7 天） |
| ② | 社区早鸟 | 6.25B | $0.000003 | 2026-11-12 → 2026-11-26（14 天） |
| ③ | 建设者轮 | 31.25B | $0.000005 | 2027-01-12 → 2027-02-02（21 天） |
| ④ | 公开轮 | 312.5B | $0.000007 | 2027-03-09 → 2027-04-08（30 天） |
| ⑤ | 最终公开轮 | 625B | $0.000009 | 2027-05-06 → 2027-06-20（45 天） |

- 价格阶梯不变：`1 / 3 / 5 / 7 / 9` µUSDC per whole TTG（约 `$0.000001` → `$0.000009`）
- 轮次之间留空档（避开圣诞与春节）。窗口是 `[start, end)`。
- `pinSaleScheduleFromNorm` 已经过 NEW 12h Timelock **execute**；五批仍 **unarmed**。公布计划 **不等于** 现在可以买入。
- **公售 USDC → NEW ProjectPool** · 永远不是 Legacy P4Cap
- Market：`0xc714E2567982ea92d5f3C5b66ab65532Cfc5f09b` · Vault：`0xe87378e49Ead2E1a422B8cae118d3C905Ee45B6C`
