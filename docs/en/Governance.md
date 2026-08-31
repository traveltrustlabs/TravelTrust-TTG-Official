# Governance

**Upstream:** Documentation Truth Baseline · Design Lock **DL_R1** · Whitepaper PASS  
**Mainnet:** `MAINNET_DEPLOYED_PHASE1` / `TIMELOCK_CUTOVER_PENDING` · **≠** Fully Active · **≠** `TT_PRODUCTION_GO`

```text
#02 Governor → #03 12h Timelock (Official PM/Vault delay **12h**)
             #15 scheduler admin = 0xe1e732…
```

- **No Safe** as V9 Official Timelock admin
- Price/batch/fee-rate/payout-map changes: governance path only
- Governance Burn: #02 → #03 → authorized burner (burn key on #01 stays pinned; this batch does not change #01)
- **#02 Governor** (~7-day holder vote, then 12h door): `0xD4b6162CB344af2C44689717edDFEe21e9082205`
- Phase1 Governor `0xA0DfC4C5C544488AfEfE696AfB8e5823911e5A9c` = **LEGACY**
- **#03 12h Timelock** (last 12h wait; anyone may execute when due): `0xF61880fe9943BBc624F487782E2fB35d8Ae50E3A`
- **#15 Scheduler** (12h admin; not treasury): `0xe1e732EfBf9B010a9204054467256d3d93f3CdD4`
- Phase1 OLD SoloTimelock **48h** `0x99e43FaBA8dC773888223f70e1dfCd18bea37D7f` = **LEGACY** (still 48h on-chain; not the living Official delay)
- Sepolia V9 periphery rehearsal is also **12h** on a **different chain/address** ([Sepolia deployments](../deployments/sepolia.md)) — **do not mix addresses**.
