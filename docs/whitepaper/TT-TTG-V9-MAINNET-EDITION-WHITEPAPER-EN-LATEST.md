# TravelTrust · TTG V9 Mainnet Edition Whitepaper

**Document ID:** `TTG_V9_MAINNET_EDITION_WHITEPAPER`  
**Edition:** Mainnet Edition · Design Lock DL_R1  
**Language:** English  
**Status:** Living Official protocol whitepaper (economics and topology)  
**Public note:** This is the English public edition.  
**Living roster:** TravelTrust Web3 release notes table 1-01 (fifteen stations). Verify every address on the Official site under Project updates and announcements, Protocol tab. Historical addresses are in the appendix and must not overlay the living roster.  
**Design Lock:** `TT-TTG-V9-OWNER-DESIGN-LOCK-LATEST`  

> **General information only**; not an offer of securities or virtual assets in any jurisdiction; not investment, tax, or legal advice. Official disclosures, terms of service, and executed agreements control.

---

## 0 · What is true now

This page is not a securities offering and not an investment offer. Trip deposits lock in USDC escrow. Exchanging TTG is a separate action, and the window is not open to the public. Governance changes wait **12 hours**. There is no written production go-live.

| Fact | Now |
|------|-----|
| Protocol deployed on Ethereum mainnet | Yes |
| Public-sale window open to the public | No |
| Written production go-live | No |

---

## 1 · Protocol positioning

TravelTrust is a decentralized travel-commerce stack:

- **Marketplace** — discovery and matching  
- **On-chain Escrow (KEEP)** — milestone-constrained release of user principal  
- **Fee / Project Pool (NEW)** — platform service fee and primary-sale USDC aggregation  
- **Role Stake (NEW)** — Region Steward TTG Seat; Merchant/Guide TTG = **`NOT_REQUIRED` / `DISABLED`** (not a default backlog); Guide performance = **per-order USDC Performance Bond** (≠ 81 Identity; full refund on success; slash only after Dispute); Merchant bond **independent / unconfirmed**; Escrow = tourist principal (orthogonal)  
- **Governance** — timed operations on the public market and vault wait twelve hours. Retired addresses are in the historical appendix.  

**TTG** is the governance / budgeting asset. It is **not** the default settlement asset for travel orders. Order principal uses allowlisted stables (**USDC** on Mainnet) and stays narratively and operationally separate from protocol-fee flows.

---

## 2 · Monetary invariants (TTG V9)

| Invariant | ACTIVE truth |
|-----------|--------------|
| Genesis supply | **25,000,000,000,000 TTG (25T)** |
| Minting | **NO-MINT** after genesis — no further mint beyond genesis supply |
| Supply decrease | **Governance Burn** only (Governor → SoloTimelock → authorized burner) |
| Token body | Non-proxy; monetary rules hard-coded in the token |
| Upgradeability | **Periphery** (Fee, Pool, Stake, Market, …) may upgrade via governance; upgrades **must not** bypass NO-MINT |

---

## 3 · Genesis allocation (50 / 35 / 3 / 5 / 7)

| Bucket | Share | Amount (TTG) | Destination (Design Lock) |
|--------|-------|--------------|---------------------------|
| Public Sale Vault | **50%** | 12.5T | NEW PublicSaleVault |
| DAO / SoloTimelock | **35%** | 8.75T | NEW SoloTimelock |
| Team | **3%** | 0.75T | `0x010365F0835323826569D61D0E13E6F8d25F6828` |
| Marketing | **5%** | 1.25T | `0xe1e732EfBf9B010a9204054467256d3d93f3CdD4` |
| Treasury / Ops | **7%** | 1.75T | `0xF34804AA66bAeE02F3aF1C540B9997C7F46b2736` |

Norm wallets (ACTIVE):

| Address | Roles |
|---------|-------|
| `0xe1e732EfBf9B010a9204054467256d3d93f3CdD4` | Deployer · SoloTimelock admin · TTG 5% |
| `0x010365F0835323826569D61D0E13E6F8d25F6828` | Team · TTG 3% |
| `0xF34804AA66bAeE02F3aF1C540B9997C7F46b2736` | Treasury / Guardian pause · Access Fee · P4 ops `to` · TTG 7% |

---

## 4 · Primary market (five Norm batches)

Primary sales run through **NEW Batch Primary Market** + **PublicSaleVault**. Norm five batches (absolute caps; do not reverse-engineer via bps):

| Batch | Cap (TTG) | USDC per 1 TTG (6-decimal raw) |
|-------|-----------|--------------------------------|
| 1 | 1.25B | 1 |
| 2 | 3.75B | 3 |
| 3 | 18.75B | 5 |
| 4 | 168.75B | 7 |
| 5 | 2,025B | 9 |

- `seedBatchesFromNorm` is SoloTimelock-gated (Phase1 **scheduled**; execute after ETA).  
- Price/batch changes: Governor → SoloTimelock; Treasury has **no** EOA direct set.  
- **Sale USDC → NEW ProjectPool**; **never** Legacy P4Cap.

---

## 5 · Platform fee & regional split (NEW CountryFeeRouter)

| Rule | ACTIVE |
|------|--------|
| Platform fee rate | **500 bps (5%)** · governance-only change |
| Active Region Steward | **45%** of platform fee → steward **registered payout wallet** · **55%** → NEW ProjectPool |
| No steward | **100%** of platform fee → NEW ProjectPool |
| Country key | Escrow/order carries ISO country; Router maps payout by country |
| globalStakers 35.75% | **EXIT** · **LEGACY / DO_NOT_USE_AS_ACTIVE_TRUTH** |
| Old “83” four-leg Fee narrative | **LEGACY** · not living ACTIVE ops semantics |

Fee callers (target): verified Escrow / Settlement paths only; Mainnet **forbids FeeIngress** as a public entry.

---

## 6 · Region Steward access fee

- **300,000 USDC** Access Fee → Treasury/Guardian `0xF34804AA66bAeE02F3aF1C540B9997C7F46b2736`  
- Stake thresholds are orthogonal (see Role Stake).

---

## 7 · Role Stake (NEW)

| Role | Status | Threshold semantics |
|------|--------|---------------------|
| Region Steward | **ACTIVE** | `minStake = live TTG.totalSupply() × country_bps / 10000` (tracks burns) |
| Merchant | **`NOT_REQUIRED` / `DISABLED`** | No TTG stake · bond rules **independent / unconfirmed** (do not inherit Guide) |
| Guide | **`NOT_REQUIRED` / `DISABLED`** | No TTG stake · performance = **per-order USDC Performance Bond** (≠ 81 Identity) |

Initial ten-country Steward bps (Design Lock deploy constants): CN/US 400 · FR/ES 450 · JP/TH 250 · SG/KR 200 · AU/AE 150.

---

## 8 · ProjectPool ops spend (P4-class)

- NEW ProjectPool is the Official sink for sale USDC and fee shares routed to the pool.  
- Ops spend: propose → SoloTimelock → `to = 0xF34804AA66bAeE02F3aF1C540B9997C7F46b2736`.  
- **Within any 90-day window, cumulative ≤ 30%** (live-cap semantics, Design Lock).  
- Legacy P4Cap `0xfB906…` = **LEGACY** · not the V9 sale sink.

---

## 9 · Governance and the 12-hour door

```text
Governor  →  12-hour door (living 0xF61880fe9943BBc624F487782E2fB35d8Ae50E3A)
             Scheduler is a person key 0xe1e732EfBf9B010a9204054467256d3d93f3CdD4 (not a contract, not treasury)
              ├─ Market / Vault / Fee / Stake / Pool
              └─ Governance burn authorization
```

- **No multi-sig is the living 12-hour-door admin.**  
- Retired multi-sig and old wait doors are in the historical appendix — do not send funds there.

---

## 10 · Mainnet architecture: NEW / KEEP / LEGACY

### NEW (V9 Official · table 1-01 living roster)

| # | Component | Living address | Doc status |
|---|---------|----------------|------------|
| 01 | TTG V9 | `0xD5c1Ef9ec730F93e324A1966bD414a7f5ebc41c9` | `DEPLOYED_PENDING_CUTOVER` |
| 02 | Governor | `0xD4b6162CB344af2C44689717edDFEe21e9082205` | Doorplate live |
| 03 | SoloTimelock (Official 12h) | `0xF61880fe9943BBc624F487782E2fB35d8Ae50E3A` | `LIVING_OFFICIAL_DELAY` |
| 04 | FeeRouterV2 | `0x2F3F4120d9d10b52f7FF762aC7E8f563454A9704` | Rules live · not called yet |
| 05 | ProjectPoolV2 | `0x65714bbF2f3B8bB7E4c71F5D51C0bbe6869dAB68` | Treasury pointer cut |
| 06 | PrimaryMarket | `0xc714E2567982ea92d5f3C5b66ab65532Cfc5f09b` | Windows not open |
| 07 | Vault | `0xe87378e49Ead2E1a422B8cae118d3C905Ee45B6C` | Admin 12h · no burn yet |
| 08 | Live trip fee contract | `0xa20a2987c688b8CAB21E1f54B6Ad103926B4082b` | Live platform-fee sink |
| 10 | RoleStake | `0xa9839Ef49e1Cc6095b41764DCf81346250A469F8` | Address final · impl old |
| 13 | Completion adapter | `0x94e2be00877c4519805408e10e16e33625863c74` | Queued for 12h |
| 14 | Pause key (person wallet, not a contract) | `0xF34804AA66bAeE02F3aF1C540B9997C7F46b2736` | Ops wallet |
| 15 | Scheduler key (person wallet, not a contract) | `0xe1e732EfBf9B010a9204054467256d3d93f3CdD4` | Ops wallet |

### KEEP (Money Path)

| Component | Address | Note |
|-----------|---------|------|
| EscrowFactoryV2Wired | `0xEE0BE3a8a8658E06c44539deD758Fb70A7f3C1C6` | KEEP |
| SettlementRouter | `0xe5C3ED16741Eb195fAE11b0C1449A79DD675B372` | KEEP · `setFeeRouter` **pending** |
| USDC | `0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48` | KEEP |

### LEGACY (DO_NOT_USE_AS_ACTIVE_TRUTH)

| Asset class | Disposition |
|-------------|-------------|
| V8 Official TTG / Primary Market / Governor | SUPERSEDED as Official V9 root |
| Remint / `R2_FINAL` / old V9 candidates | LEGACY / SUPERSEDED / DO_NOT_USE |
| Safe / KEEP Timelock / old P4Cap as V9 admin/sink | LEGACY (Safe+KEEP Timelock one-shot only) |
| Phase1 OLD SoloTimelock `0x99e43FaBA8dC773888223f70e1dfCd18bea37D7f` (48h) | LEGACY · Official PM/Vault now uses NEW 12h |
| Phase1 Governor `0xA0DfC4C5C544488AfEfE696AfB8e5823911e5A9c` | LEGACY · living Governor is table 1-01 #02 |
| Phase1 ProjectPool `0x7B21b421981A3B61cc08c8E22D4fd690E457Df37` | LEGACY · living pool is table 1-01 #05 |
| Phase1 CountryFeeRouter `0x5afD2e0C8b9fa4eecfde4bf582d3B282D28F4970` | LEGACY · not the KEEP live needle |
| Phase1 RoleStake `0xf6A1Fb4435E463117a666818611F49D03F91E7A7` | LEGACY · living seat is table 1-01 #10 |
| `globalStakers` / old “83” four-leg ACTIVE ops | EXIT / LEGACY |

---

## 11 · Security model (summary)

- Token: **NO-MINT** · no public holder burn · Governance Burn via Timelock.  
- Fee: 5% baseline · governance-only rate changes · country payouts Timelock-written.  
- Pool: 90d ≤ 30% ops cap · ops recipient fixed to Treasury.  
- Stake: Steward live supply × bps ACTIVE · Merchant/Guide TTG = **NOT_REQUIRED / DISABLED** · Guide performance = per-order USDC Bond (≠ 81) · Merchant bond independent/unconfirmed · Escrow orthogonal.  
- Governance wait door: **12 hours**. The scheduler is a person key, not a treasury.  
- This document does not issue a production go-live.

---

## 12 · V8 / old-V9 Legacy Policy

1. Historical evidence **must not be deleted or rewritten**; mark LEGACY / SUPERSEDED / HISTORICAL / DO_NOT_USE_AS_ACTIVE_TRUTH only.  
2. Any external ACTIVE narrative must cite this Mainnet Edition or the Documentation Truth Baseline.  
3. Sepolia Candidate, Remint, and R2_FINAL PASS **must not** be claimed as Mainnet Official ACTIVE.  
4. Official www copy / GitHub Official Docs / Production `/meta` · Indexer cutover are **out of scope** for automatic execution by this whitepaper.

---

## 13 · Risks and boundaries

- Current chain state is **Phase1 / cutover pending**; batches may be unseeded; Fee may not yet point to NEW Router.  
- Regulatory, tax, and jurisdictional access are separate matters; this document is not legal advice.  
- **Production GO** remains **NO_GO**; this file does not issue go-live.

---

## Key points

- Trip deposits use USDC escrow. TTG is the governance token; the exchange window is not open.  
- Genesis split 50 / 35 / 3 / 5 / 7; 25 trillion supply; no mint.  
- Living governance wait is **12 hours**. Stations 14 and 15 are person keys, not contracts.  
- Retired addresses live only in the historical appendix — do not send funds there.  
- This page is not a securities offering and does not issue a written production go-live.
