# Governance

**Upstream:** TravelTrust Web3 release notes **table 1-01** · **≠** Fully Active · **≠** `TT_PRODUCTION_GO`

```text
02 Governor → 03 12h door (Official delay **12h**)
              15 scheduler admin = 0xee05e6BcC658D3f3900Cc1CACeBE9eef8DbB40B1
```

- **No Safe** as V9 Official Timelock admin
- Price / batch / fee / payout map changes: governance path only
- Governance burn: 02 → 03 → authorized burner (01 burn key stays locked)
- **#02 Governor:** `0xf9D9143bB632096ABeFd943D894c43C04fD16ED4` (old `0xD4b6162C…` RETIRED · do not queue old #1)
- Phase1 Governor `0xA0DfC4C5C544488AfEfE696AfB8e5823911e5A9c` = **LEGACY**
- **#03 12h Timelock:** `0xafaee79259c831630E6f7Dc5B8885E0Fbe27fb5F` (delay=43200 · **do not execute old 03** `0xF61880fe…`)
- **#15 Scheduler** (deploy / 12h admin · genesis 5% · P4 ops payee): `0xee05e6BcC658D3f3900Cc1CACeBE9eef8DbB40B1` (old EOA `0xe1e732…` is not this role)
- Phase1 OLD SoloTimelock **48h** `0x99e43FaBA8dC773888223f70e1dfCd18bea37D7f` = **LEGACY**
- Sepolia is a different chain — **do not mix addresses**.
