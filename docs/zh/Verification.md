# 验证

**上游：** Documentation Truth Baseline · Design Lock **DL_R1** · Whitepaper PASS  
**Mainnet：** `MAINNET_DEPLOYED_PHASE1` / `TIMELOCK_CUTOVER_PENDING` · **≠** Fully Active · **≠** `TT_PRODUCTION_GO`

- TTG V9 Phase1 源码已在 Etherscan 验证（creation bytecode Exact Match 路径见 runbook）
- 公开文档地址必须与 Documentation Truth Baseline Exact 一致
- Gate：`python scripts/dev/run-ttg-v9-github-official-alignment-gate.py --require-zero`
- 禁止为浏览器展示修改 DL_R1 源码或 Phase1 地址
