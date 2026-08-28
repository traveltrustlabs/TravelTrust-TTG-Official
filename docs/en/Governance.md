# Governance

**Upstream:** Documentation Truth Baseline · Design Lock **DL_R1** · Whitepaper PASS  
**Mainnet:** `MAINNET_DEPLOYED_PHASE1` / `TIMELOCK_CUTOVER_PENDING` · **≠** Fully Active · **≠** `TT_PRODUCTION_GO`

```text
Governor → SoloTimelock (Official PM/Vault delay **12h**)
             admin = Marketing Norm 0xe1e732…
```

- **No Safe** as V9 Official Timelock admin
- Price/batch/fee-rate/payout-map changes: governance path only
- Governance Burn: Governor → SoloTimelock → authorized burner
- Phase1 Governor: `0xA0DfC4C5C544488AfEfE696AfB8e5823911e5A9c`
- Official PM/Vault delay after PATH_A: NEW SoloTimelock **12h** `0xF61880fe9943BBc624F487782E2fB35d8Ae50E3A`
- Phase1 OLD SoloTimelock **48h** `0x99e43FaBA8dC773888223f70e1dfCd18bea37D7f` = **LEGACY** (still 48h on-chain; not the living Official delay)
- Sepolia V9 periphery rehearsal is also **12h** on a **different chain/address** ([Sepolia deployments](../deployments/sepolia.md)) — **do not mix addresses**.
