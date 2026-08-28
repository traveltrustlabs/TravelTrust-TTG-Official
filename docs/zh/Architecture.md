# 架构

**上游：** Documentation Truth Baseline · `V9_DOCUMENTATION_FULL_CONVERGENCE_PASS` · `TTG_V9_MAINNET_EDITION_WHITEPAPER_PASS` · Design Lock **DL_R1**  
**Mainnet：** `MAINNET_DEPLOYED_PHASE1` / `TIMELOCK_CUTOVER_PENDING` · **≠** Fully Active · **≠** `TT_PRODUCTION_GO`

TravelTrust Web3 Mainnet Edition 采用 **NEW / KEEP / LEGACY** 三分：

| 类别 | 含义 |
|------|------|
| **NEW** | V9 Official Token、SoloTimelock、Governor、Vault、Market、ProjectPool、CountryFeeRouter、RoleStake |
| **KEEP** | EscrowFactoryV2Wired + SettlementRouter + USDC 资金面（用户本金） |
| **LEGACY** | Safe / 旧 Timelock / P4Cap / V8 / Remint / R2_FINAL — **不入** ACTIVE 合约登记 |

```text
订单(+ISO 国家) → KEEP Escrow / Settlement
  → 平台费 5% → NEW CountryFeeRouter
       ├─ 有主理人 → 45% 登记钱包 / 55% NEW ProjectPool
       └─ 无主理人 → 100% NEW ProjectPool
公售 USDC → NEW ProjectPool（永远不是 Legacy P4Cap）
Governor → SoloTimelock 12h (Official PM/Vault) → 外围运维 / Governance Burn
  （Phase1 OLD 48h SoloTimelock = LEGACY）
```

Token 货币规则 **NO-MINT 不可增发**。外围可经治理升级，**不得**借升级绕过 NO-MINT。
