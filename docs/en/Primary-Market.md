# Primary Market

**Upstream:** Documentation Truth Baseline · Design Lock **DL_R1** · Whitepaper PASS  
**Mainnet remint V1:** five-round calendar is in Norm constants (round 1 **2026-11-12 09:00 UTC**). Seeded in the genesis transaction. Exchange windows still follow the calendar; buying before start reverts. **≠** Fully Active

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
| 14 | Pause | Pause sale; 300k access. Not P4 ops spend |
| 15 | Scheduler | 12h admin; genesis 5%; **P4 ops payee** |

#11 factory / #12 SettlementRouter / #04 fee router / #10 RoleStake / #08 empty slot (not deployed) / #13 adapter are the **trip money path**, not the sale counter. Full roster: [Contract Registry](Contract-Registry.md).

| Round | Name | Cap (TTG) | ~ USDC / 1 TTG | UTC window |
|-------|------|-----------|----------------|------------|
| 1 | Genesis calibration | 1.25B | $0.000001 | 2026-11-12 → 2026-11-19 (7d) |
| 2 | Community early bird | 6.25B | $0.000003 | 2026-12-03 → 2026-12-17 (14d) |
| 3 | Builder round | 31.25B | $0.000005 | 2027-01-14 → 2027-02-04 (21d) |
| 4 | Public round | 312.5B | $0.000007 | 2027-02-25 → 2027-03-27 (30d) |
| 5 | Final public round | 625B | $0.000009 | 2027-04-08 → 2027-05-23 (45d) |

- Price ladder unchanged: `1 / 3 / 5 / 7 / 9` µUSDC per whole TTG (about `$0.000001` → `$0.000009`)
- Gaps between rounds skip US Thanksgiving, Christmas/New Year, Lunar New Year 2027, and Easter 2027. Round 4 opens after Lantern Festival and closes before Easter; round 5 opens after Easter (45d; PRC Labour Day falls inside). Windows are `[start, end)`.
- Calendar is in remint Norm constants; seeded in genesis. A published plan is **not** a live buy window until UTC 09:00.
- **Sale USDC → table 1-01 · 05 ProjectPoolV2** `0x55cBeD4460Ad2bCc0a9F2598af5013415B121d61` · never Legacy P4Cap / old pool `0x7B21…`. Old `0x65714bbF…` RETIRED.
- **06 PrimaryMarket:** `0xEaB632241C9c93B9012fc60a834d2D771E620130` · **07 Vault:** `0x5Ce1f7A8a9560aFf257B184F012e87B7ee2f3A6A` · schedule pin via **03 12h Timelock** `0xafaee79259c831630E6f7Dc5B8885E0Fbe27fb5F`. Old `0xc714…` / `0xe873…` RETIRED; do not treat as live.
