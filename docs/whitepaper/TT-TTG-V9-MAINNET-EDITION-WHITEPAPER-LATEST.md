# TravelTrust · TTG V9 Mainnet Edition Whitepaper（中文正式版）

**Document ID:** `TTG_V9_MAINNET_EDITION_WHITEPAPER`  
**Edition:** Mainnet Edition · Design Lock **DL_R1**  
**Language:** zh-CN  
**STATUS:** Living Official protocol whitepaper for TTG V9 economics & topology  
**Public edition:** derived from Design Lock DL_R1 documentation baseline (private monorepo not published).
**Design Lock:** `TT-TTG-V9-OWNER-DESIGN-LOCK-LATEST`  
**EN twin:** [`TT-TTG-V9-MAINNET-EDITION-WHITEPAPER-EN-LATEST.md`](TT-TTG-V9-MAINNET-EDITION-WHITEPAPER-EN-LATEST.md)  
**Public review:** documentation-only pack in this repository (no private CI gates).

> **一般性信息**；不构成任何司法辖区的发售要约、证券或虚拟资产要约，亦不构成投资、税务或法律建议。正式披露以发布公告、用户协议及双方签署文本为准。

---

## 0 · 链上状态机（写死）

| 状态 | 含义 | 当前 |
|------|------|------|
| `MAINNET_DEPLOYED_PHASE1` / `DEPLOYED_PENDING_CUTOVER` / `TIMELOCK_CUTOVER_PENDING` | V9 栈与 Genesis 已部署；Solo 定时操作与 KEEP `setFeeRouter` **未完成** | **YES** |
| `MAINNET_FULLY_ACTIVE` / `ACTIVE_OFFICIAL` | Solo execute + KEEP SettlementRouter→NEW CountryFeeRouter + Reality 验证完成 | **NO** |
| `TT_PRODUCTION_GO` | Owner 独立书面 Production GO | **NO_GO**（本白皮书不签发） |

**纪律：** 本文描述 Design Lock **目标协议语义**与 Phase1 **已部署事实**；**禁止**将当前 Mainnet 表述为 Fully Active Official。

---

## 1 · 协议定位

TravelTrust 是去中心化旅行商业协议栈：

- **Marketplace** — 发现与撮合  
- **On-chain Escrow（KEEP）** — 里程碑资金约束与释放  
- **Fee / Project Pool（NEW）** — 平台服务费与公售 USDC 归集  
- **Role Stake（NEW）** — 区域主理人 TTG Seat；Merchant/Guide TTG = **`NOT_REQUIRED` / `DISABLED`**（非默认待办）；向导履约 = **逐订单 USDC Performance Bond**（≠ 81 Identity；完成返还 · Dispute 后可罚没）；商家 Bond **独立未确认**；Escrow = 游客本金正交  
- **Governance（NEW）** — Official PM/Vault 定时操作延迟 **12h** NEW SoloTimelock；Phase1 OLD 48h SoloTimelock 在 PATH_A 之后为 **LEGACY**  

**TTG** 是协议治理与预算程序资产，**不是**旅行订单默认结算资产。订单本金以允许列表内稳定币（Mainnet 以 **USDC**）为主，并与协议费路径分轨。

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
| Team | **3%** | 0.75T | `0x010365…` |
| Marketing | **5%** | 1.25T | `0xe1e732…` |
| Treasury / Ops | **7%** | 1.75T | `0xF34804…` |

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

- **300,000 USDC** Access Fee → Treasury/Guardian `0xF34804…`  
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
- 运营拨付：propose → SoloTimelock → `to = 0xF34804…`。  
- **90 天窗口内累计 ≤ 30%**（live-cap 语义，Design Lock）。  
- Legacy P4Cap `0xfB906…` = **LEGACY** · 非 V9 公售 sink。

---

## 9 · 治理与 Timelock

```text
Governor  →  SoloTimelock Official delay = 12h (NEW 0xF61880fe…, admin = 0xe1e732…)
             Phase1 OLD 48h 0x99e43F… = LEGACY after PATH_A
              ├─ Market / Vault / Fee / Stake / Pool ops
              └─ Governance Burn 授权路径
```

- **无 Safe 作为 V9 Official Timelock admin。**  
- Legacy Safe `0x96491…` + KEEP Timelock `0x50F0…`：**仅**允许一次性 KEEP SettlementRouter `setFeeRouter(NEW CountryFeeRouter)`；完成后仍属 **LEGACY**，不得升格为 V9 Official 治理根。

---

## 10 · Mainnet 架构：NEW / KEEP / LEGACY

### NEW（V9 Official）

| 组件 | Phase1 地址 | 文档状态 |
|------|-------------|----------|
| TTG V9 | `0xD5c1Ef9ec730F93e324A1966bD414a7f5ebc41c9` | `DEPLOYED_PENDING_CUTOVER` |
| SoloTimelock（Official 12h） | `0xF61880fe9943BBc624F487782E2fB35d8Ae50E3A` | `LIVING_OFFICIAL_DELAY` |
| SoloTimelock（Phase1 OLD 48h） | `0x99e43FaBA8dC773888223f70e1dfCd18bea37D7f` | `LEGACY` after PATH_A |
| ProjectPool | `0x7B21b421981A3B61cc08c8E22D4fd690E457Df37` | `DEPLOYED_PENDING_CUTOVER` |
| CountryFeeRouter | `0x5afD2e0C8b9fa4eecfde4bf582d3B282D28F4970` | `DEPLOYED_PENDING_CUTOVER` |
| Vault | `0xe87378e49Ead2E1a422B8cae118d3C905Ee45B6C` | `DEPLOYED_PENDING_CUTOVER` |
| Market | `0xc714E2567982ea92d5f3C5b66ab65532Cfc5f09b` | `DEPLOYED_PENDING_CUTOVER` |
| Governor | `0xA0DfC4C5C544488AfEfE696AfB8e5823911e5A9c` | `DEPLOYED_PENDING_CUTOVER` |
| RoleStake | `0xf6A1Fb4435E463117a666818611F49D03F91E7A7` | `DEPLOYED_PENDING_CUTOVER` |

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
| `globalStakers` / 83 旧 Fee 四腿 ACTIVE 运营 | EXIT / LEGACY |

---

## 11 · 安全模型（摘要）

- Token：**NO-MINT** · 无公开 holder burn · Governance Burn 经 Timelock。  
- Fee：固定 5% 起点 · 变更仅治理 · 国家 payout 经 Timelock 写入。  
- Pool：90d≤30% 运营上限 · ops 收款固定 Treasury。  
- Stake：Steward live supply × bps ACTIVE · Merchant/Guide TTG = **NOT_REQUIRED / DISABLED** · Guide 履约 = 逐订单 USDC Bond（≠ 81）· Merchant Bond 独立未确认 · Escrow 正交。  
- Official SoloTimelock：**12h** 延迟（PM/Vault）· admin = Marketing Norm · **≠ Safe**。Phase1 OLD **48h** `0x99e43F…` = **LEGACY**。  
- AI triad + Sepolia DL_R1 regression + Mainnet Pre-Broadcast Final 为审计候选路径证据；**不等价** `TT_PRODUCTION_GO`。

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
- **Production GO** 仍需 Owner 书面裁决；本文件 **STOP** 于白皮书 PASS，不翻转 `TT_PRODUCTION_GO`。

---

## 中文要点

- 正式白皮书 = **Design Lock DL_R1** 语义 + Phase1 地址事实。  
- 25T / NO-MINT · 50/35/3/5/7 · 五批一级市场 · USDC→ProjectPool · 5% · 45/55 或 100% · 30万准入 · Steward live Role Stake · Merchant/Guide TTG NOT_REQUIRED/DISABLED · 90d≤30% · Official SoloTimelock **12h**（OLD 48h LEGACY）。  
- **无** globalStakers / 83 ACTIVE / R2_FINAL ACTIVE / 旧 P4Cap 公售 / Safe 作 V9 admin（均为 **LEGACY / DO_NOT_USE_AS_ACTIVE_TRUTH**）。  
- Mainnet = **`MAINNET_DEPLOYED_PHASE1` / `TIMELOCK_CUTOVER_PENDING`** · **≠ Fully Active** · **≠ Production GO**。
