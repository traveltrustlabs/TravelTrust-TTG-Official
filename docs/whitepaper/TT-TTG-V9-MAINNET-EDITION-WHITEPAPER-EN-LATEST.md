# TravelTrust · TTG V9 Mainnet Edition Whitepaper (English)

**Document ID:** `TTG_V9_MAINNET_EDITION_WHITEPAPER`  
**Edition:** Mainnet Edition · Design Lock **DL_R1**  
**Language:** en-US  
**STATUS:** Living Official protocol whitepaper for TTG V9 economics & topology  
**Public edition:** derived from Design Lock DL_R1 documentation baseline (private monorepo not published).
**Design Lock:** `TT-TTG-V9-OWNER-DESIGN-LOCK-LATEST`  
**ZH twin:** [`TT-TTG-V9-MAINNET-EDITION-WHITEPAPER-LATEST.md`](TT-TTG-V9-MAINNET-EDITION-WHITEPAPER-LATEST.md)  
**Public review:** documentation-only pack in this repository (no private CI gates).

> **General information only**; not an offer of securities or virtual assets in any jurisdiction; not investment, tax, or legal advice. Official disclosures, terms of service, and executed agreements control.

---

## 0 · On-chain status machine (hard)

| State | Meaning | Now |
|-------|---------|-----|
| `MAINNET_DEPLOYED_PHASE1` / `DEPLOYED_PENDING_CUTOVER` / `TIMELOCK_CUTOVER_PENDING` | V9 stack + Genesis deployed; Solo timed ops and KEEP `setFeeRouter` **not** finished | **YES** |
| `MAINNET_FULLY_ACTIVE` / `ACTIVE_OFFICIAL` | After Solo execute + KEEP SettlementRouter → NEW CountryFeeRouter + Reality verify | **NO** |
| `TT_PRODUCTION_GO` | Independent Owner written Production GO | **NO_GO** (this whitepaper does not issue GO) |

**Discipline:** This edition states Design Lock **target semantics** and Phase1 **deployed facts**. It **must not** claim Mainnet is Fully Active Official.

---

## 1 · Protocol positioning

TravelTrust is a decentralized travel-commerce stack:

- **Marketplace** — discovery and matching  
- **On-chain Escrow (KEEP)** — milestone-constrained release of user principal  
- **Fee / Project Pool (NEW)** — platform service fee and primary-sale USDC aggregation  
- **Role Stake (NEW)** — Region Steward TTG Seat; Merchant/Guide TTG = **`NOT_REQUIRED` / `DISABLED`** (not a default backlog); Guide performance = **per-order USDC Performance Bond** (≠ 81 Identity; full refund on success; slash only after Dispute); Merchant bond **independent / unconfirmed**; Escrow = tourist principal (orthogonal)  
- **Governance (NEW)** — Official PM/Vault timed-ops delay **12h** NEW SoloTimelock; Phase1 OLD 48h SoloTimelock is **LEGACY** after PATH_A  

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
| Team | **3%** | 0.75T | `0x010365…` |
| Marketing | **5%** | 1.25T | `0xe1e732…` |
| Treasury / Ops | **7%** | 1.75T | `0xF34804…` |

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

- **300,000 USDC** Access Fee → Treasury/Guardian `0xF34804…`  
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
- Ops spend: propose → SoloTimelock → `to = 0xF34804…`.  
- **Within any 90-day window, cumulative ≤ 30%** (live-cap semantics, Design Lock).  
- Legacy P4Cap `0xfB906…` = **LEGACY** · not the V9 sale sink.

---

## 9 · Governance and Timelock

```text
Governor  →  SoloTimelock Official delay = 12h (NEW 0xF61880fe…, admin = 0xe1e732…)
             Phase1 OLD 48h 0x99e43F… = LEGACY after PATH_A
              ├─ Market / Vault / Fee / Stake / Pool ops
              └─ Governance Burn authorization path
```

- **No Safe as V9 Official Timelock admin.**  
- Legacy Safe `0x96491…` + KEEP Timelock `0x50F0…`: allowed **only** for one-shot KEEP SettlementRouter `setFeeRouter(NEW CountryFeeRouter)`; afterward remain **LEGACY**, never promoted to V9 Official governance root.

---

## 10 · Mainnet architecture: NEW / KEEP / LEGACY

### NEW (V9 Official)

| Component | Phase1 address | Doc status |
|-----------|----------------|------------|
| TTG V9 | `0xD5c1Ef9ec730F93e324A1966bD414a7f5ebc41c9` | `DEPLOYED_PENDING_CUTOVER` |
| SoloTimelock (Official 12h) | `0xF61880fe9943BBc624F487782E2fB35d8Ae50E3A` | `LIVING_OFFICIAL_DELAY` |
| SoloTimelock (Phase1 OLD 48h) | `0x99e43FaBA8dC773888223f70e1dfCd18bea37D7f` | `LEGACY` after PATH_A |
| ProjectPool | `0x7B21b421981A3B61cc08c8E22D4fd690E457Df37` | `DEPLOYED_PENDING_CUTOVER` |
| CountryFeeRouter | `0x5afD2e0C8b9fa4eecfde4bf582d3B282D28F4970` | `DEPLOYED_PENDING_CUTOVER` |
| Vault | `0xe87378e49Ead2E1a422B8cae118d3C905Ee45B6C` | `DEPLOYED_PENDING_CUTOVER` |
| Market | `0xc714E2567982ea92d5f3C5b66ab65532Cfc5f09b` | `DEPLOYED_PENDING_CUTOVER` |
| Governor | `0xA0DfC4C5C544488AfEfE696AfB8e5823911e5A9c` | `DEPLOYED_PENDING_CUTOVER` |
| RoleStake | `0xf6A1Fb4435E463117a666818611F49D03F91E7A7` | `DEPLOYED_PENDING_CUTOVER` |

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
| `globalStakers` / old “83” four-leg ACTIVE ops | EXIT / LEGACY |

---

## 11 · Security model (summary)

- Token: **NO-MINT** · no public holder burn · Governance Burn via Timelock.  
- Fee: 5% baseline · governance-only rate changes · country payouts Timelock-written.  
- Pool: 90d ≤ 30% ops cap · ops recipient fixed to Treasury.  
- Stake: Steward live supply × bps ACTIVE · Merchant/Guide TTG = **NOT_REQUIRED / DISABLED** · Guide performance = per-order USDC Bond (≠ 81) · Merchant bond independent/unconfirmed · Escrow orthogonal.  
- Official SoloTimelock: **12h** delay (PM/Vault) · admin = Marketing Norm · **≠ Safe**. Phase1 OLD **48h** `0x99e43F…` = **LEGACY**.  
- AI triad + Sepolia DL_R1 regression + Mainnet Pre-Broadcast Final are audit-candidate evidence; **not** `TT_PRODUCTION_GO`.

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
- **Production GO** still requires Owner written verdict; this file **STOP**s at whitepaper PASS and does **not** flip `TT_PRODUCTION_GO`.

---

## Key points

- Official whitepaper = **Design Lock DL_R1** semantics + Phase1 address facts.  
- 25T / NO-MINT · 50/35/3/5/7 · five-batch primary market · USDC→ProjectPool · 5% · 45/55 or 100% · 300k access · Steward live Role Stake · Merchant/Guide TTG NOT_REQUIRED/DISABLED · 90d≤30% · Official SoloTimelock **12h** (OLD 48h LEGACY).  
- **No** globalStakers / “83” ACTIVE / R2_FINAL ACTIVE / old-P4Cap sale sink / Safe-as-V9-admin (all **LEGACY / DO_NOT_USE_AS_ACTIVE_TRUTH**).  
- Mainnet = **`MAINNET_DEPLOYED_PHASE1` / `TIMELOCK_CUTOVER_PENDING`** · **≠ Fully Active** · **≠ Production GO**.
