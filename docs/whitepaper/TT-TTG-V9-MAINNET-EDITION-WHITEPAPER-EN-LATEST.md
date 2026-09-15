# TravelTrust Whitepaper

TravelTrust is a decentralized travel-commerce protocol. Travelers lock trip deposits in USDC escrow. TTG is for governance and Region Steward seats, not the default settlement asset for orders. Addresses follow the Official Protocol page. Send funds only to addresses listed here.

> General information only. This is not an offer of securities or virtual assets in any jurisdiction, and not investment, tax, or legal advice. Terms of service and executed agreements control.

---

## 0 · What is true now

Trip deposits can lock in escrow under the protocol. Exchanging TTG is separate, and the window is not open to the public. The traveler App is in development and not listed on App Store or Google Play. There is no written production go-live.

| Fact | Now |
|------|-----|
| Protocol deployed on Ethereum mainnet | Yes |
| Public-sale window open to the public | No |
| Traveler App listed on App Store / Google Play | No |
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
| Public sale vault | 50% | 12.5T | #07 `0x1c9dBa15eBFB31Dd4BDa608b7b003B3ba4a61287` |
| DAO treasury | 35% | 8.75T | DAO `0x063174C62A2878eB8E6c033363b8f1bA1aE9cE3b` (admin = #03) |
| Team | 3% | 0.75T | `0xfBe514a0863e8F8278Fe8996F8F83CCa28734A81` |
| Marketing | 5% | 1.25T | #15 `0xee05e6BcC658D3f3900Cc1CACeBE9eef8DbB40B1` |
| Treasury / ops | 7% | 1.75T | #14 `0xe3DE92DcB96396E75093A873C231Bb9Dd050346E` |

#15 is the 12-hour-delay admin and the project-pool ops payee. #14 is the pause key and the 300,000 USDC access-fee payee. 35% does **not** sit in the 12-hour door itself.

---

## 5 · Public exchange (five batches)

Primary sales run through the batch market and public-sale vault. The window is not open to the public. Caps, prices, and UTC windows match Official www. Together the five windows are about **3.905%** of 25T (**976.25 billion TTG**). Unsold remainder may be burned in part; a burn is not price protection.

| Batch | Name | Cap (TTG) | USDC / 1 TTG | UTC window |
|-------|------|-----------|--------------|------------|
| 1 | Genesis calibration | 1,250,000,000 | 0.00000100 | 2026-11-12 09:00 → 2026-11-19 09:00 |
| 2 | Community early bird | 6,250,000,000 | 0.00000300 | 2026-12-03 09:00 → 2026-12-17 09:00 |
| 3 | Builder round | 31,250,000,000 | 0.00000500 | 2027-01-14 09:00 → 2027-02-04 09:00 |
| 4 | Public round | 312,500,000,000 | 0.00000700 | 2027-02-25 09:00 → 2027-03-27 09:00 |
| 5 | Final public round | 625,000,000,000 | 0.00000900 | 2027-04-08 09:00 → 2027-05-23 09:00 |

Batch writes and price changes go through a governance vote and the 12-hour delay. Sale USDC goes to the project pool. A published plan is not a live buy.

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

The Region Steward access fee is 300,000 USDC to `0xe3DE92DcB96396E75093A873C231Bb9Dd050346E`. It funds the founding team’s start-up costs: protocol development, security and infrastructure, early operations, and payroll. It is separate from the TTG seat stake and is not refundable in the ordinary course.

---

## 8 · Project pool

The project pool collects sale USDC and platform-fee shares routed to the pool. Ops spend: propose → 12-hour delay → `0xee05e6BcC658D3f3900Cc1CACeBE9eef8DbB40B1`. Cumulative spend in any 90-day window is at most 30%.

---

## 9 · Governance delay

```text
Governor  →  12-hour delay (0x2Cb9f0FD770B50931f0a4cd463113bBA39331acb)
             Scheduler is #15 0xee05e6BcC658D3f3900Cc1CACeBE9eef8DbB40B1
             (person key, not treasury)
              ├─ Market / Vault / Fee / Stake / Pool
              └─ Governance burn authorization
```

No multi-sig administers the 12-hour delay. Send funds only to addresses listed on this page.

---

## 10 · Checkable addresses

Official www lists 01 / 06 / 09. Full V2 roster: [Contract Registry](../en/Contract-Registry.md).

| # | Name | Address | Note |
|---|------|---------|------|
| 01 | TTG | `0xd9965802ff0A9DAB5d0E13392dA797cd6D13ee51` | Living token · 25T |
| 02 | Governor | `0x69fF62475C3ed36B3B8627BfEC980b3047B3bf42` | Living |
| 03 | 12h Timelock | `0x2Cb9f0FD770B50931f0a4cd463113bBA39331acb` | Living door |
| 05 | Project pool | `0xD49F33c1f1d806500407550f8e92b0d1b3d725d9` | Sale USDC sink |
| 06 | Primary market | `0xaB1D74A62e3fBB1c140a9Dfa9bB5b7Fe3F8C7e46` | Seeded · not open |
| 07 | Vault | `0x1c9dBa15eBFB31Dd4BDa608b7b003B3ba4a61287` | Genesis 12.5T |
| DAO | 35% treasury | `0x063174C62A2878eB8E6c033363b8f1bA1aE9cE3b` | 8.75T · admin = #03 |
| 09 | Circle USDC | `0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48` | KEEP |
| 3% | Team | `0xfBe514a0863e8F8278Fe8996F8F83CCa28734A81` | Genesis 0.75T |
| 5% / 15 | Marketing / scheduler | `0xee05e6BcC658D3f3900Cc1CACeBE9eef8DbB40B1` | Genesis 1.25T |
| 7% / 14 | Treasury / pause | `0xe3DE92DcB96396E75093A873C231Bb9Dd050346E` | Genesis 1.75T |

Token Update 32×32 SVG: `https://www.web3-ttg.com/brand/token/ttg-logo-32.svg`. Do not send funds to lost-key 01 `0xD5c1Ef9e…` or Phase1 06 `0xc714E256…`.

---

## 11 · Security, scope, and risk

No mint after genesis. Holders cannot burn. Governance burn waits 12 hours. Platform fee starts at 5%. Pool ops spend is capped at 30% in any 90-day window. This document states living rules and checkable addresses. It does not rewrite the website or observer layer, and it does not issue go-live.

Conversion is not open. The traveler App is in development and not listed on stores. Regulatory, tax, and jurisdictional access are separate. Production GO remains NO_GO.

---


## 12 · Official contact

Official human project email: `traveltrust.ir@gmail.com`.

`noreply@web3-ttg.com` is system mail for verification codes and transactional notices only. It is not a human listing or Token Update identity.

Whether Etherscan requires a mailbox on the official domain remains an external reviewer rule. `ETHERSCAN_EMAIL_DOMAIN_MATCH` is **UNKNOWN**. Publishing Gmail as the real official mailbox does not make Token Info item 5 PASS.

## 13 · Attribution

| Role | Name | Public checks |
|------|------|---------------|
| Founder / Maintainer | Sebastian Ward | Website `/team/founder` · X `@swardtm` · GitHub `wejfiowej124234` |
| Maintainer | Helena Berger | Website `/team/clo` · GitHub `yinhang744-dev` |
| Maintainer | Rasmus Saar | Website `/team/engineer_a` · GitHub `TT-Cc19873` |

Official GitHub: https://github.com/traveltrustlabs/TravelTrust-TTG-Official. The official repository is a project record, not Founder-authored commits. This paper does not claim Founder commits there and does not claim public organization or collaborator membership. Project email: `traveltrust.ir@gmail.com`. There is no LinkedIn. This paper does not claim degrees, employer history, or third-party endorsements.

## Key points

- Trip deposits use USDC escrow. TTG is for governance and seats; the exchange window is not open.
- Region Steward staking locks TTG; yield is that country’s real platform fee (living 45/55, reconfigurable by governance proposal), not inflation rewards. The 300,000 USDC access fee is a start-up cost, not a stake.
- Genesis split 50 / 35 / 3 / 5 / 7; 25 trillion supply; no mint.
- Governance waits 12 hours. Stations 14 and 15 are person keys, not contracts.
- This page is not a securities offering and does not issue a written production go-live.

Document ID: `TTG_V9_MAINNET_EDITION_WHITEPAPER`.
