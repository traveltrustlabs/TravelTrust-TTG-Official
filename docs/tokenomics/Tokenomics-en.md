# Tokenomics

**Upstream:** Documentation Truth Baseline · Design Lock **DL_R1** · Whitepaper PASS  
**Mainnet:** `MAINNET_DEPLOYED_PHASE1` / `TIMELOCK_CUTOVER_PENDING` · **≠** Fully Active

> Phase1 Norm wallet addresses below are **design-disclosure** facts from the whitepaper §0 — **not** the Wave 2 Mainnet registry pack (published after V9 Mainnet Reality).

## Genesis (50 / 35 / 3 / 5 / 7)

| Bucket | Share | Amount | Destination |
|--------|-------|--------|-------------|
| Public Sale Vault | 50% | 12.5T | new 07 `0x5Ce1f7A8…3A6A` |
| Governed DAO Treasury | 35% | 8.75T | `0x6fc3Be4999DE2Ad648C70e72076a66A7cB90a3c1` (admin=03; 03 is the door, not the vault) |
| Team | 3% | 0.75T | `0xfBe514a0863e8F8278Fe8996F8F83CCa28734A81` |
| Marketing | 5% | 1.25T | new 15 `0xee05e6BcC658D3f3900Cc1CACeBE9eef8DbB40B1` |
| Treasury / pause | 7% | 1.75T | new 14 `0xe3DE92DcB96396E75093A873C231Bb9Dd050346E` |

## Living person keys

| Address | Roles |
|---------|-------|
| `0xee05e6BcC658D3f3900Cc1CACeBE9eef8DbB40B1` | 15 · deploy/schedule · genesis 5% · P4 ops payee |
| `0xfBe514a0863e8F8278Fe8996F8F83CCa28734A81` | genesis 3% |
| `0xe3DE92DcB96396E75093A873C231Bb9Dd050346E` | 14 · pause · genesis 7% · 300k access. **Not** P4 ops |

Retired EOAs `0xe1e732…` / `0x010365…` / `0xF34804…` are **not** living roles. They may be ordinary test wallets.

## Explicit exits (not ACTIVE)

- `globalStakers` **35.75%** = **EXIT / LEGACY**
- Old “83” four-leg Fee ACTIVE ops = **LEGACY**
