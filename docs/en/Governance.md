# Governance

**Facts:** TravelTrust Web3 发布说明 **V2** table 1-01  
**Mainnet:** contracts deployed · conversion not open · **≠** Fully Active · **≠** `TT_PRODUCTION_GO`

```text
#02 Governor → #03 12h Timelock (delay 43200)
             #15 scheduler admin = 0xee05e6BcC658D3f3900Cc1CACeBE9eef8DbB40B1
```

- **No Safe** as V9 Official Timelock admin
- Price/batch/fee-rate/payout-map changes: governance path only
- Governance Burn: #02 → #03 → authorized burner (burn key on #01 stays pinned)
- **#02 Governor** (~7-day holder vote, then 12h door): `0x69fF62475C3ed36B3B8627BfEC980b3047B3bf42`
- **#03 12h Timelock** (last 12h wait; the door is not a treasury): `0x2Cb9f0FD770B50931f0a4cd463113bBA39331acb`
- **#15 Scheduler** (12h admin; 5% marketing key; not treasury): `0xee05e6BcC658D3f3900Cc1CACeBE9eef8DbB40B1`
- Phase1 Governor `0xD4b6162CB344af2C44689717edDFEe21e9082205` and earlier `0xA0DfC4C5C544488AfEfE696AfB8e5823911e5A9c` = **LEGACY**
- Phase1 12h Timelock `0xF61880fe9943BBc624F487782E2fB35d8Ae50E3A` = **LEGACY** (not the living V2 door)
- Phase1 48h SoloTimelock `0x99e43FaBA8dC773888223f70e1dfCd18bea37D7f` = **LEGACY**
- Phase1 scheduler `0xe1e732EfBf9B010a9204054467256d3d93f3CdD4` = **LEGACY**
- Sepolia rehearsal is also **12h** on a **different chain/address** ([Sepolia](../deployments/sepolia.md)) — **do not mix addresses**.
