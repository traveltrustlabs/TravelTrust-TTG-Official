# SUPERSEDED — do not use as living public disclosure

**SUPERSEDED 2026-09-15** by [PUBLIC-DISCLOSURE-LISTING-READINESS-CANDIDATE-20260915.md](PUBLIC-DISCLOSURE-LISTING-READINESS-CANDIDATE-20260915.md) and [PUBLIC-DISCLOSURE-LISTING-READINESS-REALITY-20260915.md](PUBLIC-DISCLOSURE-LISTING-READINESS-REALITY-20260915.md).

This file is a **historical** alignment pack. Official www pin `f438ad803` is **not** the living website. Living Official www is `e31df9c9c5…` · Fly `deployment-01M2JJ0TDN99SNBJ7SPHE0AF5C`. The public GitHub freeze parent is `918fef193`. Do **not** treat this document as current identity, contact, or pin.

---

# Public Disclosure Alignment Candidate · 2026-09-15 (historical)

**Status:** SUPERSEDED · kept for provenance only · **not** the listing-readiness Candidate.  
**`TT_PRODUCTION_GO`:** NO_GO  
**Plane:** `traveltrustlabs/TravelTrust-TTG-Official` public docs only. Internal V9 engineering / Official www / API / Postgres / App / contracts **not** modified.  
**Working copy (historical note):** the 2026-09-15 alignment working copy had **no `.git`**. Living Candidate is now git worktree `D:/TravelTrust-TTG-Official-cand-listing-readiness-20260915` from `918fef193`.

## Facts used

| Source | Role |
|--------|------|
| `D:/TravelTrust-V1.1-wt-ttg-remint/docs/web3/TravelTrust-Web3-发布说明-V2.md` (+ HTML) | Contract / token SSOT |
| Official www Verified Baseline `f438ad803` | Display SSOT for 01/06/09, five-round listing, App copy, logo |
| `D:/TravelTrust-TTG-APP/PROJECT.md` §0 | App Reality: P6 in development · stores not listed · TTG convert is www-only |

## Item verification (this pass)

| # | Item | Expected (V2) | Local public files | Result |
|---|------|---------------|--------------------|--------|
| 1 | 01 | `0xd9965802ff0A9DAB5d0E13392dA797cd6D13ee51` | README, Registry, TTG-V9, RELEASE-NOTES, whitepaper §10 | PASS |
| 2 | 02 | `0x69fF62475C3ed36B3B8627BfEC980b3047B3bf42` | Registry, Governance, whitepaper §9–10 | PASS |
| 3 | 03 | `0x2Cb9f0FD770B50931f0a4cd463113bBA39331acb` delay=43200 | Registry, Governance, Security, whitepaper §9 | PASS |
| 4 | 05 | `0xD49F33c1f1d806500407550f8e92b0d1b3d725d9` | Registry, ProjectPool, CountryFeeRouter, Primary-Market | PASS |
| 5 | 06 | `0xaB1D74A62e3fBB1c140a9Dfa9bB5b7Fe3F8C7e46` | Registry, Primary-Market, RELEASE-NOTES, whitepaper §10 | PASS |
| 6 | 09 | `0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48` | Registry, Primary-Market, whitepaper §10 | PASS (KEEP) |
| 7 | 3% | `0xfBe514a0863e8F8278Fe8996F8F83CCa28734A81` | Tokenomics, whitepaper §4/§10, Registry affiliates | PASS |
| 8 | 5% / 15 | `0xee05e6BcC658D3f3900Cc1CACeBE9eef8DbB40B1` | Tokenomics, ProjectPool ops payee, whitepaper §4/§8/§9 | PASS |
| 9 | 7% / 14 | `0xe3DE92DcB96396E75093A873C231Bb9Dd050346E` | Tokenomics, access-fee payee, whitepaper §4/§7 | PASS |
| 10 | DAO 35% | `0x063174C62A2878eB8E6c033363b8f1bA1aE9cE3b` (admin=#03) | Tokenomics, whitepaper §4/§10, Registry affiliates | PASS · 35% **not** in the 12h door |
| 11 | 25T · 50/35/3/5/7 | Unchanged | README, RELEASE-NOTES, whitepaper §3–4 | PASS |
| 12 | Five-round UTC + price | Official listing 2026-11-12 09:00 … 2027-05-23; 0.00000100→0.00000900; caps 1.25B/6.25B/31.25B/312.5B/625B | RELEASE-NOTES, Primary-Market, whitepaper §5, PDFs | PASS |
| 13 | 32×32 SVG | Official portrait `ttg-logo-32.svg` | `assets/logo/ttg-logo-32.svg` | PASS |
| 14 | Contract Registry | V2 table 1-01 + DAO/Activity/3% affiliates | `docs/en\|zh/Contract-Registry.md` | PASS (08 not deployed) |
| 15 | Whitepaper markdown | §4/7/8/9/10 aligned to V2 | `docs/whitepaper/*-LATEST.md` | PASS |
| 16 | Whitepaper PDF | Regenerated from current markdown | EN 7p · ZH 7p · key V2 strings present · Phase1 3%/5%/7%/02/03 absent | PASS |
| 17 | Mainnet / App / links | contracts deployed · conversion not open · App in development · stores not listed | README, CONTACT, Mainnet-Deployments, Verification | PASS |
| 18 | Hub copies | governance + tokenomics hubs = en/zh pages | `docs/governance/*` · `docs/tokenomics/*` | PASS |

## Zero-check (2026-09-15 local scan · 51 md/pdf/svg files)

| Check | Result |
|-------|--------|
| Phase1 02/03/05 / 3%/5%/7% as **living** current | **0** FAIL |
| Same addresses as **LEGACY / do-not-send** | Allowed (Legacy-Policy, Governance, Tokenomics, ProjectPool, CountryFeeRouter, Registry warn, Primary-Market warn) |
| Old living calendar `2026-10-15` / `2027-01-12` / `2027-03-09` / `2027-05-06` | **0** |
| Old caps `3.75B / 18.75B / 168.75B / 2025B` | **0** |
| `DEPLOYED_PENDING_CUTOVER` as living status | **0** (CHANGELOG one historical line, marked SUPERSEDED) |
| Contradiction “35% = 12h delay contract” | **0** |
| Internal satellite / alignment-gate URLs as current source | **0** |
| PDF vs markdown key V2 strings | **0 miss** (3%, 5%/15, 7%/14, DAO, 02, 03, 05, 2026-11-12, 2027-05-23, 0.00000900) |

### Phase1 / lost-key (LEGACY only · must not appear as living)

```
01 lost     0xD5c1Ef9ec730F93e324A1966bD414a7f5ebc41c9
01 V1 remint 0x01dc2706c4E0F82995d63042c06873d1DC6B3AEa
02          0xD4b6162CB344af2C44689717edDFEe21e9082205
03          0xF61880fe9943BBc624F487782E2fB35d8Ae50E3A
04          0x2F3F4120d9d10b52f7FF762aC7E8f563454A9704
05          0x65714bbF2f3B8bB7E4c71F5D51C0bbe6869dAB68
06          0xc714E2567982ea92d5f3C5b66ab65532Cfc5f09b
10          0xa9839Ef49e1Cc6095b41764DCf81346250A469F8
5%/sched    0xe1e732EfBf9B010a9204054467256d3d93f3CdD4
3%          0x010365F0835323826569D61D0E13E6F8d25F6828
7%/pause    0xF34804AA66bAeE02F3aF1C540B9997C7F46b2736
```

## What changed in this second pass (vs leftover table)

| Surface | Before | After |
|---------|--------|-------|
| Whitepaper §4 | Phase1 3%/5%/7% + “35% = 12h delay contract” | V2 3%/15/14 + DAO `0x063174…` |
| Whitepaper §7 access fee | `0xF34804…` | #14 `0xe3DE92…` |
| Whitepaper §8 pool ops | `0xF34804…` | #15 `0xee05e6…` |
| Whitepaper §9 Governor/Timelock | Phase1 `0xF61880…` / `0xe1e732…` | V2 #03 / #15 |
| Whitepaper §10 | 01/06/09 only | + 02/03/05/07/DAO/3%/5%/7% |
| `docs/governance/*` hubs | Stale Phase1 living cites | Overwritten from `docs/en\|zh/Governance.md` |
| `docs/tokenomics/*` hubs | Stale 3%/5%/7% | Overwritten from `docs/en\|zh/Tokenomics.md` |
| Contract Registry affiliates | Missing DAO/Activity/3% | Added + keep do-not-send |
| TTG-V9 burn path | “SoloTimelock” (48h name) | 12h Timelock |
| CHANGELOG `DEPLOYED_PENDING_CUTOVER` | Looked living | Marked historical SUPERSEDED |
| PDFs | 2026-08-31 bytes still had Phase1 3%/5%/7%/03 | Regenerated from current MD via pandoc HTML → pymupdf |

## PDF regeneration note

- Engine: pandoc 3.9.0.2 markdown→HTML, then PyMuPDF `Story` → A4 PDF, `garbage=4` + deflate.
- EN: `docs/whitepaper/TT-TTG-V9-MAINNET-EDITION-WHITEPAPER-EN-LATEST.pdf`
- ZH: `docs/whitepaper/TT-TTG-V9-MAINNET-EDITION-WHITEPAPER-LATEST.pdf` (CJK font embed; larger than the stale 350k file; **content** matches markdown).
- Temporary `_tmp-*.html` removed.

## Left for Owner (not this Agent)

| Item | Why |
|------|-----|
| Copy this working tree into the **real** `traveltrustlabs/TravelTrust-TTG-Official` clone | This copy has no `.git` |
| Owner PASS then commit/push | Explicitly withheld |
| Official www / API / App / contracts | Out of scope · unchanged |
| `TT_PRODUCTION_GO` | Remains **NO_GO** |

Internal satellite HTML URL is not a current source. No deploy scripts, keys, or V9 procedure published.
