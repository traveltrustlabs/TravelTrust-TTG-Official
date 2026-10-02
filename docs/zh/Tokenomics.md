# 代币经济

**上游：** Documentation Truth Baseline · Design Lock **DL_R1** · Whitepaper PASS  
**Mainnet：** `MAINNET_DEPLOYED_PHASE1` / `TIMELOCK_CUTOVER_PENDING` · **≠** Fully Active

> 下文 Phase1 Norm 钱包地址为白皮书 §0 **设计披露事实** — **非** Wave 2 主网登记包（V9 Mainnet Reality 后发布）。

## Genesis（50 / 35 / 3 / 5 / 7）

| 桶 | 比例 | 数量 | 落点 |
|----|------|------|------|
| Public Sale Vault | 50% | 12.5T | 新 07 `0x5Ce1f7A8…3A6A` |
| Governed DAO Treasury | 35% | 8.75T | `0x6fc3Be4999DE2Ad648C70e72076a66A7cB90a3c1`（admin=03，03 是门不是仓） |
| Team | 3% | 0.75T | `0xfBe514a0863e8F8278Fe8996F8F83CCa28734A81` |
| Marketing | 5% | 1.25T | 新 15 `0xee05e6BcC658D3f3900Cc1CACeBE9eef8DbB40B1` |
| Treasury / pause | 7% | 1.75T | 新 14 `0xe3DE92DcB96396E75093A873C231Bb9Dd050346E` |

## 现行人钥

| 地址 | 角色 |
|------|------|
| `0xee05e6BcC658D3f3900Cc1CACeBE9eef8DbB40B1` | 15 · 部署/预约 · 创世 5% · 项目池运营取款 |
| `0xfBe514a0863e8F8278Fe8996F8F83CCa28734A81` | 创世 3% |
| `0xe3DE92DcB96396E75093A873C231Bb9Dd050346E` | 14 · 暂停 · 创世 7% · 30 万准入。**不是**运营取款 |

旧 EOA `0xe1e732…` / `0x010365…` / `0xF34804…` **不是**现行角色，可当普通测试钱包。

## 明确退出（非 ACTIVE）

- `globalStakers` **35.75%** = **EXIT / LEGACY**
- 旧「83」四腿 Fee ACTIVE 运营 = **LEGACY**
