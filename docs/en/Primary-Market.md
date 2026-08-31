# Primary Market

**Upstream:** Documentation Truth Baseline · Design Lock **DL_R1** · Whitepaper PASS  
**Mainnet:** Sale schedule pin `V9_SHORT_WINDOW_FIVE_ROUND` (Timelock execute 2026-08-26). Exchange windows are **not open to the public**. **≠** Fully Active · **≠** `TT_PRODUCTION_GO`

Five short Norm windows via NEW Batch Primary Market + PublicSaleVault (Official release names: Genesis calibration / Community early bird / Builder round / Public round / Final public round; about **3.905%** of 25T).

**Web3 SSOT is table 1-01.** Machines that *are* the TTG sale (jobs locked with the Canvas):

| # | Name | Does |
|---|------|------|
| 01 | Governance token | Vote, sale, steward metering; no mint |
| 03 | 12h Timelock | Last 12h wait; anyone may execute when due |
| 05 | ProjectPoolV2 | Sale USDC and no-seat fees land here |
| 06 | PrimaryMarket | Five short windows; this five locked |
| 07 | Vault | Genesis 50% TTG; unsold returns; burn via 12h |
| 09 | USDC | Circle USD; sale, deposits, access fee |
| 14 | Pause | Pause sale; default wage and 300k payee |
| 15 | Scheduler | 12h admin; not treasury |

#11 factory / #12 SettlementRouter / #04 fee router / #10 RoleStake / #08 next fee router / #13 adapter are the **trip money path**, not the sale counter. Full roster: [Contract Registry](Contract-Registry.md).

| Round | Name | Cap (TTG) | ~ USDC / 1 TTG | UTC window |
|-------|------|-----------|----------------|------------|
| 1 | Genesis calibration | 1.25B | $0.000001 | 2026-10-15 → 2026-10-22 (7d) |
| 2 | Community early bird | 6.25B | $0.000003 | 2026-11-12 → 2026-11-26 (14d) |
| 3 | Builder round | 31.25B | $0.000005 | 2027-01-12 → 2027-02-02 (21d) |
| 4 | Public round | 312.5B | $0.000007 | 2027-03-09 → 2027-04-08 (30d) |
| 5 | Final public round | 625B | $0.000009 | 2027-05-06 → 2027-06-20 (45d) |

- Price ladder unchanged: `1 / 3 / 5 / 7 / 9` µUSDC per whole TTG (about `$0.000001` → `$0.000009`)
- Gaps between rounds skip Christmas and Lunar New Year. Windows are `[start, end)`.
- `pinSaleScheduleFromNorm` already **executed** on the NEW 12h Timelock; all five batches remain **unarmed**. A published plan is **not** a live buy window.
- **Sale USDC → table 1-01 · 05 ProjectPoolV2** `0x65714bbF2f3B8bB7E4c71F5D51C0bbe6869dAB68` · never Legacy P4Cap / old pool `0x7B21…`
- **06 PrimaryMarket:** `0xc714E2567982ea92d5f3C5b66ab65532Cfc5f09b` · **07 Vault:** `0xe87378e49Ead2E1a422B8cae118d3C905Ee45B6C` · schedule pin via **03 12h Timelock**
