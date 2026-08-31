# TravelTrust Whitepaper

TravelTrust is a decentralized travel-commerce protocol. Travelers lock trip deposits in USDC escrow. TTG is for governance and Region Steward seats, not the default settlement asset for orders. Addresses follow the Official Protocol page. Send funds only to addresses listed here.

> General information only. This is not an offer of securities or virtual assets in any jurisdiction, and not investment, tax, or legal advice. Terms of service and executed agreements control.

---

## 0 · What is true now

Trip deposits can lock in escrow under the protocol. Exchanging TTG is separate, and the window is not open to the public. Governance changes wait 12 hours. There is no written production go-live.

| Fact | Now |
|------|-----|
| Protocol deployed on Ethereum mainnet | Yes |
| Public-sale window open to the public | No |
| Written production go-live | No |

---

## 1 · What the protocol does

The protocol splits a travel sale into checkable on-chain paths:

- Marketplace: discovery and matching
- Escrow: milestone lock and release of traveler principal (USDC on mainnet)
- Platform fee: 5% on verified trips, split by country
- Region Steward: stake TTG for a seat and share that country’s real platform fees — not minted rewards
- Governance: sale, vault, and parameter changes wait 12 hours

Merchants and guides do not stake TTG by default. Their performance uses order-side bonds, separate from steward seats.

---

## 2 · Region Steward: a different staking model

Many tokens use lock-and-emit staking to dampen sell pressure: depositors earn a low APR, often paid by inflation. TravelTrust does not.

Applying as a country’s Region Steward *is* the stake: TTG locks to the country threshold. Steward income comes from travel that already happened in that country — 45% of the platform fee to the steward’s registered wallet, 55% to the project pool (the split can be negotiated with the team and community, and reconfigured by governance proposal). With no seated steward, 100% of the platform fee goes to the pool.

TTG cannot mint after genesis, so steward pay cannot be printed as new tokens. The seat threshold is live supply × country bps / 10000, and it falls when supply is burned. A 300,000 USDC access fee goes to the operations wallet and is counted separately from the stake. It pays the founding team’s start-up costs: protocol development, security and infrastructure, early operations, and payroll. It is not a stake and does not count toward the seat threshold.

That does two jobs at once: TTG is locked in a governance seat, and the staker shares real regional flow instead of a low APR unrelated to sales.

Initial ten-country bps: CN/US 400 · FR/ES 450 · JP/TH 250 · SG/KR 200 · AU/AE 150. The seat-contract upgrade is still waiting on the 12-hour delay. The fee split is already in the fee rules.

---

## 3 · Monetary rules

| Rule | Meaning |
|------|---------|
| Genesis supply | 25,000,000,000,000 TTG (25T) |
| Minting | No further mint after genesis |
| Supply decrease | Governance burn only: vote → 12-hour delay → authorized burner |
| Token body | Non-proxy; monetary rules live in the token |
| Upgrades | Periphery may upgrade via governance; upgrades must not bypass the no-mint rule |

---

## 4 · Genesis allocation (50 / 35 / 3 / 5 / 7)

| Bucket | Share | Amount | Destination |
|--------|-------|--------|-------------|
| Public sale vault | 50% | 12.5T | PublicSaleVault |
| Governance treasury / 12-hour delay | 35% | 8.75T | 12-hour delay contract |
| Team | 3% | 0.75T | `0x010365F0835323826569D61D0E13E6F8d25F6828` |
| Marketing | 5% | 1.25T | `0xe1e732EfBf9B010a9204054467256d3d93f3CdD4` |
| Treasury / ops | 7% | 1.75T | `0xF34804AA66bAeE02F3aF1C540B9997C7F46b2736` |

`0xe1e732…CdD4` is also the deployer and 12-hour-delay admin. `0xF34804…2736` is also the pause key, access-fee recipient, and ops-spend recipient.

---

## 5 · Public exchange (five batches)

Primary sales run through the batch market and public-sale vault. The window is not open to the public. Caps are absolute:

| Batch | Cap (TTG) | USDC per 1 TTG (6-decimal raw) |
|-------|-----------|--------------------------------|
| 1 | 1.25B | 1 |
| 2 | 3.75B | 3 |
| 3 | 18.75B | 5 |
| 4 | 168.75B | 7 |
| 5 | 2,025B | 9 |

Batch writes and price changes go through a governance vote and the 12-hour delay. Treasury cannot change prices from an ordinary wallet. Sale USDC goes to the project pool.

---

## 6 · Platform fee and country split

| Rule | Meaning |
|------|---------|
| Platform fee rate | 500 bps (5%), governance-only change |
| Seated steward | 45% to the steward registered wallet, 55% to the project pool (negotiable with team and community; reconfigurable by governance proposal) |
| No steward | 100% to the project pool |
| Country key | Escrow orders carry an ISO country code |

Fees come only from verified escrow / settlement paths. There is no separate holder dividend.

---

## 7 · Merchants, guides, and the access fee

| Role | TTG stake | Performance |
|------|-----------|-------------|
| Region Steward | Active; see section 2 | Seat plus country platform-fee share |
| Merchant | Not required | Bond rules independent and unconfirmed |
| Guide | Not required | Per-order USDC performance bond |

The Region Steward access fee is 300,000 USDC to `0xF34804AA66bAeE02F3aF1C540B9997C7F46b2736`. It funds the founding team’s start-up costs: protocol development, security and infrastructure, early operations, and payroll. It is separate from the TTG seat stake and is not refundable in the ordinary course.

---

## 8 · Project pool

The project pool collects sale USDC and platform-fee shares routed to the pool. Ops spend: propose → 12-hour delay → `0xF34804AA66bAeE02F3aF1C540B9997C7F46b2736`. Cumulative spend in any 90-day window is at most 30%.

---

## 9 · Governance delay

```text
Governor  →  12-hour delay (0xF61880fe9943BBc624F487782E2fB35d8Ae50E3A)
             Scheduler is an operations wallet 0xe1e732EfBf9B010a9204054467256d3d93f3CdD4
             (not a contract, not treasury)
              ├─ Market / Vault / Fee / Stake / Pool
              └─ Governance burn authorization
```

No multi-sig administers the 12-hour delay. Send funds only to addresses listed on this page.

---

## 10 · Checkable addresses

| # | Name | Address | Note |
|---|------|---------|------|
| 01 | TTG | `0xD5c1Ef9ec730F93e324A1966bD414a7f5ebc41c9` | Deployed; cutover incomplete |
| 02 | Governor | `0xD4b6162CB344af2C44689717edDFEe21e9082205` | Deployed |
| 03 | 12-hour delay | `0xF61880fe9943BBc624F487782E2fB35d8Ae50E3A` | Official delay |
| 04 | Fee router | `0x2F3F4120d9d10b52f7FF762aC7E8f563454A9704` | Rules deployed; not yet called |
| 05 | Project pool | `0x65714bbF2f3B8bB7E4c71F5D51C0bbe6869dAB68` | Sale proceeds point here |
| 06 | Primary market | `0xc714E2567982ea92d5f3C5b66ab65532Cfc5f09b` | Batches not open to the public |
| 07 | Vault | `0xe87378e49Ead2E1a422B8cae118d3C905Ee45B6C` | Gated by the 12-hour delay |
| 08 | Live trip fee contract | `0xa20a2987c688b8CAB21E1f54B6Ad103926B4082b` | Current platform-fee sink |
| 10 | Role stake | `0xa9839Ef49e1Cc6095b41764DCf81346250A469F8` | Implementation upgrade queued |
| 13 | Completion adapter | `0x94e2be00877c4519805408e10e16e33625863c74` | Upgrade queued |
| 14 | Pause key (person wallet) | `0xF34804AA66bAeE02F3aF1C540B9997C7F46b2736` | Operations wallet |
| 15 | Scheduler key (person wallet) | `0xe1e732EfBf9B010a9204054467256d3d93f3CdD4` | Operations wallet |

Trip money path: escrow factory `0xEE0BE3a8a8658E06c44539deD758Fb70A7f3C1C6` · settlement router `0xe5C3ED16741Eb195fAE11b0C1449A79DD675B372` · USDC `0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48`.

---

## 11 · Security, scope, and risk

No mint after genesis. Holders cannot burn. Governance burn waits 12 hours. Platform fee starts at 5%. Pool ops spend is capped at 30% in any 90-day window. This document states living rules and checkable addresses. It does not rewrite the website or observer layer, and it does not issue go-live.

Cutover is still incomplete: batches may be unseeded, fees may not yet point to the new router, and the seat implementation is queued. Regulatory, tax, and jurisdictional access are separate. Production GO remains NO_GO.

---

## Key points

- Trip deposits use USDC escrow. TTG is for governance and seats; the exchange window is not open.
- Region Steward staking locks TTG; yield is that country’s real platform fee (living 45/55, reconfigurable by governance proposal), not inflation rewards. The 300,000 USDC access fee is a start-up cost, not a stake.
- Genesis split 50 / 35 / 3 / 5 / 7; 25 trillion supply; no mint.
- Governance waits 12 hours. Stations 14 and 15 are person keys, not contracts.
- This page is not a securities offering and does not issue a written production go-live.

Document ID: `TTG_V9_MAINNET_EDITION_WHITEPAPER`.
