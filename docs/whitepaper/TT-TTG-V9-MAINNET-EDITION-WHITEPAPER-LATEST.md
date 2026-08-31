# TravelTrust · TTG V9 主网版白皮书

**文档编号：** `TTG_V9_MAINNET_EDITION_WHITEPAPER`  
**版本：** 主网版 · 设计锁定 DL_R1  
**语言：** 中文  
**状态：** 现网协议白皮书（经济与拓扑）  
**公开说明：** 供公众阅读的正式文本。  
**活名册：** 以 TravelTrust Web3 发布说明「表 1-01 · 十五台」为准。请到官网「项目动态与公告」的「协议」页核对全部地址。第一阶段旧简表地址标为历史，不得当作现网活地址。  
**设计锁定：** `TT-TTG-V9-OWNER-DESIGN-LOCK-LATEST`  

> **一般性信息**；不构成任何司法辖区的发售要约、证券或虚拟资产要约，亦不构成投资、税务或法律建议。正式披露以发布公告、用户协议及双方签署文本为准。

---

## 0 · 现在能做什么

本页不是证券发行，也不是投资要约。行程订金用 USDC 锁进托管合约；换 TTG 是另一件事，且兑换窗口尚未对公众开放。治理改规则要等 **12 小时**。没有书面生产放行。

| 事实 | 现在 |
|------|------|
| 协议已部署在以太坊主网 | 是 |
| 公售窗口对公众开放 | 否 |
| 书面生产放行 | 否 |

---

## 1 · 协议定位

TravelTrust 是去中心化旅行商业协议栈：

- **市场** — 发现与撮合  
- **链上托管** — 按里程碑锁定并释放游客本金  
- **平台费与项目美元池** — 平台服务费与公售美元归集  
- **角色质押** — 区域主理人用 TTG 占席；商家与向导默认不质押 TTG；向导履约用逐订单美元保证金（完成返还，争议后可罚没）；商家保证金规则独立未确认；托管本金与此正交  
- **治理** — 公售柜台与币库的定时操作延迟十二小时。已退役地址见文末历史附录。  

**TTG** 是协议治理与预算程序资产，**不是**旅行订单默认结算资产。订单本金以允许列表内稳定币（主网以 **USDC**）为主，并与协议费路径分轨。

---

## 2 · 货币不变量（TTG V9）

| 不变量 | ACTIVE 真值 |
|--------|-------------|
| Genesis 总量 | **25,000,000,000,000 TTG（25T）** |
| 增发 | **NO-MINT** — Genesis 后永远不可再 mint 超过 Genesis 供给 |
| 供给减少 | 仅经 **Governance Burn** 路径（Governor → SoloTimelock → 授权 burner） |
| 代币本体 | 非代理；货币规则硬编码于 Token |
| 可治理升级 | **外围协议**（Fee、Pool、Stake、Market 等）可经治理升级；**不得**借升级绕过 NO-MINT |

---

## 3 · Genesis 分配（50 / 35 / 3 / 5 / 7）

| 桶 | 比例 | 数量（TTG） | 落点（Design Lock） |
|----|------|-------------|---------------------|
| Public Sale Vault | **50%** | 12.5T | NEW PublicSaleVault |
| DAO / SoloTimelock | **35%** | 8.75T | NEW SoloTimelock |
| Team | **3%** | 0.75T | `0x010365F0835323826569D61D0E13E6F8d25F6828` |
| Marketing | **5%** | 1.25T | `0xe1e732EfBf9B010a9204054467256d3d93f3CdD4` |
| Treasury / Ops | **7%** | 1.75T | `0xF34804AA66bAeE02F3aF1C540B9997C7F46b2736` |

Norm 钱包角色（ACTIVE）：

| 地址 | 角色 |
|------|------|
| `0xe1e732EfBf9B010a9204054467256d3d93f3CdD4` | Deployer · SoloTimelock admin · TTG 5% |
| `0x010365F0835323826569D61D0E13E6F8d25F6828` | Team · TTG 3% |
| `0xF34804AA66bAeE02F3aF1C540B9997C7F46b2736` | Treasury/Guardian pause · Access Fee · P4 ops `to` · TTG 7% |

---

## 4 · 一级市场（五批 Norm）

公售通过 **NEW Batch Primary Market** + **PublicSaleVault** 执行。Norm 五批（绝对 cap，不以 bps 反推）：

| Batch | Cap（TTG） | USDC / 1 TTG（6 decimals raw） |
|-------|------------|--------------------------------|
| 1 | 1.25B | 1 |
| 2 | 3.75B | 3 |
| 3 | 18.75B | 5 |
| 4 | 168.75B | 7 |
| 5 | 2,025B | 9 |

- `seedBatchesFromNorm` 仅经 **SoloTimelock**（Phase1 已 schedule，**待 ETA 后 execute**）。  
- 价格/批次变更：Governor → SoloTimelock；Treasury **不得** EOA 直改。  
- **公售 USDC → NEW ProjectPool**；**永远不是** Legacy P4Cap。

---

## 5 · 平台服务费与区域分账（NEW CountryFeeRouter）

| 规则 | ACTIVE |
|------|--------|
| 平台费率 | **500 bps（5%）** · 仅治理可改 |
| 有 Active 区域主理人 | 平台费中 **45%** → 主理人**登记钱包** · **55%** → NEW ProjectPool |
| 无主理人 | 平台费 **100%** → NEW ProjectPool |
| 国家键 | Escrow/订单携带 ISO country · Router 按国家映射 payout |
| globalStakers 35.75% | **EXIT** · **LEGACY / DO_NOT_USE_AS_ACTIVE_TRUTH** |
| 旧 83 四腿 Fee 叙事 | **LEGACY** · 不以 ACTIVE 运营语义引用 |

Fee 调用方（目标）：仅已验证 Escrow / Settlement 路径；Mainnet **禁止 FeeIngress** 作为公开入口。

---

## 6 · 区域主理人准入费

- **300,000 USDC** Access Fee → Treasury/Guardian `0xF34804AA66bAeE02F3aF1C540B9997C7F46b2736`  
- 质押门槛另见 Role Stake（与 Access Fee 正交）。

---

## 7 · Role Stake（NEW）

| 角色 | 状态 | 门槛语义 |
|------|------|----------|
| Region Steward | **ACTIVE** | `minStake = live TTG.totalSupply() × country_bps / 10000`（随 burn 下降） |
| Merchant | **`NOT_REQUIRED` / `DISABLED`** | 不质押 TTG · 履约押规则 **独立未确认**（不继承 Guide） |
| Guide | **`NOT_REQUIRED` / `DISABLED`** | 不质押 TTG · 履约 = **逐订单 USDC Performance Bond**（≠ 81 Identity） |

十国初始 Steward bps（Design Lock 部署常量）：CN/US 400 · FR/ES 450 · JP/TH 250 · SG/KR 200 · AU/AE 150。

---

## 8 · ProjectPool 运营拨付（P4 类）

- NEW ProjectPool 为 Official 公售 USDC 与无主理人/主理人份额汇入的总池。  
- 运营拨付：propose → SoloTimelock → `to = 0xF34804AA66bAeE02F3aF1C540B9997C7F46b2736`。  
- **90 天窗口内累计 ≤ 30%**（live-cap 语义，Design Lock）。  
- Legacy P4Cap `0xfB906…` = **LEGACY** · 非 V9 公售 sink。

---

## 9 · 治理与等待门

```text
投票机  →  12 小时门（活地址 0xF61880fe9943BBc624F487782E2fB35d8Ae50E3A）
             预约钥是人钥 0xe1e732EfBf9B010a9204054467256d3d93f3CdD4（不是合约、不是国库）
              ├─ 公售 / 币库 / 费用 / 席位 / 资金池
              └─ 治理销毁授权
```

- **没有把多签当作现网 12 小时门的管理员。**  
- 已退役多签与旧等待门见文末历史附录，请勿向其转账。

---

## 10 · Mainnet 架构：NEW / KEEP / LEGACY

### NEW（V9 Official · 表 1-01 活名册）

| # | 组件 | 活地址 | 文档状态 |
|---|------|--------|----------|
| 01 | TTG V9 | `0xD5c1Ef9ec730F93e324A1966bD414a7f5ebc41c9` | `DEPLOYED_PENDING_CUTOVER` |
| 02 | Governor | `0xD4b6162CB344af2C44689717edDFEe21e9082205` | 门牌齐 |
| 03 | SoloTimelock（Official 12h） | `0xF61880fe9943BBc624F487782E2fB35d8Ae50E3A` | `LIVING_OFFICIAL_DELAY` |
| 04 | FeeRouterV2 | `0x2F3F4120d9d10b52f7FF762aC7E8f563454A9704` | 规则在 · 没人喊 |
| 05 | ProjectPoolV2 | `0x65714bbF2f3B8bB7E4c71F5D51C0bbe6869dAB68` | 收款口已切 |
| 06 | PrimaryMarket | `0xc714E2567982ea92d5f3C5b66ab65532Cfc5f09b` | 五轮未开售 |
| 07 | Vault | `0xe87378e49Ead2E1a422B8cae118d3C905Ee45B6C` | 钥 12h · 未烧 |
| 08 | 行程平台费合约（现行） | `0xa20a2987c688b8CAB21E1f54B6Ad103926B4082b` | 现行平台费落点 |
| 10 | RoleStake | `0xa9839Ef49e1Cc6095b41764DCf81346250A469F8` | 实现旧 · upgrade 已预约 |
| 13 | Completion adapter | `0x94e2be00877c4519805408e10e16e33625863c74` | 已预约等 12h |
| 14 | 暂停钥（人钥，不是合约） | `0xF34804AA66bAeE02F3aF1C540B9997C7F46b2736` | 运营钱包 |
| 15 | 预约钥（人钥，不是合约） | `0xe1e732EfBf9B010a9204054467256d3d93f3CdD4` | 运营钱包 |

### KEEP（Money Path）

| 组件 | 地址 | 说明 |
|------|------|------|
| EscrowFactoryV2Wired | `0xEE0BE3a8a8658E06c44539deD758Fb70A7f3C1C6` | KEEP |
| SettlementRouter | `0xe5C3ED16741Eb195fAE11b0C1449A79DD675B372` | KEEP · `setFeeRouter` **pending** |
| USDC | `0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48` | KEEP |

### LEGACY（DO_NOT_USE_AS_ACTIVE_TRUTH）

| 资产 | 处置 |
|------|------|
| V8 Official TTG / Primary Market / Governor | SUPERSEDED as Official V9 root |
| Remint / `R2_FINAL` / 旧 V9 Candidate | LEGACY / SUPERSEDED / DO_NOT_USE |
| Safe / KEEP Timelock / 旧 P4Cap 作为 V9 admin/sink | LEGACY（Safe+KEEP Timelock 仅 one-shot 切针） |
| Phase1 OLD SoloTimelock `0x99e43FaBA8dC773888223f70e1dfCd18bea37D7f`（48h） | LEGACY · Official PM/Vault 已用 NEW 12h |
| Phase1 Governor `0xA0DfC4C5C544488AfEfE696AfB8e5823911e5A9c` | LEGACY · 活投票机为表 1-01 #02 |
| Phase1 ProjectPool `0x7B21b421981A3B61cc08c8E22D4fd690E457Df37` | LEGACY · 活池为表 1-01 #05 |
| Phase1 CountryFeeRouter `0x5afD2e0C8b9fa4eecfde4bf582d3B282D28F4970` | LEGACY · 非 KEEP 活针 |
| Phase1 RoleStake `0xf6A1Fb4435E463117a666818611F49D03F91E7A7` | LEGACY · 活席位为表 1-01 #10 |
| `globalStakers` / 83 旧 Fee 四腿 ACTIVE 运营 | EXIT / LEGACY |

---

## 11 · 安全模型（摘要）

- Token：**NO-MINT** · 无公开 holder burn · Governance Burn 经 Timelock。  
- Fee：固定 5% 起点 · 变更仅治理 · 国家 payout 经 Timelock 写入。  
- Pool：90d≤30% 运营上限 · ops 收款固定 Treasury。  
- Stake：Steward live supply × bps ACTIVE · Merchant/Guide TTG = **NOT_REQUIRED / DISABLED** · Guide 履约 = 逐订单 USDC Bond（≠ 81）· Merchant Bond 独立未确认 · Escrow 正交。  
- 治理等待门：**12 小时**。预约钥是人钥，不是国库。  
- 本文件不作生产放行。

---

## 12 · V8 / 旧 V9 Legacy Policy

1. 历史证据 **不得删除或篡改**；仅可标记 LEGACY / SUPERSEDED / HISTORICAL / DO_NOT_USE_AS_ACTIVE_TRUTH。  
2. 任何对外 ACTIVE 叙述必须引用本 Mainnet Edition 或 Documentation Truth Baseline。  
3. 禁止把 Sepolia Candidate、Remint、R2_FINAL PASS 冒充 Mainnet Official ACTIVE。  
4. 官网文案 / GitHub Official Docs / Production `/meta` · Indexer 切针 **不在本白皮书权限内自动执行**。

---

## 13 · 风险与边界

- 当前链上状态为 **Phase1 / cutover pending**；公售批次可能尚未 seed；Fee 可能尚未切到 NEW Router。  
- 监管、税务、司法辖区准入另案；本文不作法律意见。  
- 书面生产放行仍为 **NO_GO**；本文件不签发。

---

## 中文要点

- 行程订金用 USDC 托管；TTG 是治理代币，兑换窗口尚未开放。  
- 创世分配 50 / 35 / 3 / 5 / 7；总量 25 万亿，不能增发。  
- 现网治理等待 **12 小时**。14、15 号是人钥，不是合约。  
- 已退役地址只放在历史附录，请勿向其转账。  
- 本页不是证券发行，也没有书面生产放行。
