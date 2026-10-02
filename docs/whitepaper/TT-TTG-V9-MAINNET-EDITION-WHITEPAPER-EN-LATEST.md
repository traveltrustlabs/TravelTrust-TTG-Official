# TravelTrust Whitepaper

> **Lost-TTG remint.** Living roster is [Official protocol](https://www.web3-ttg.com/protocol) table 1-01. Old 01–08/10–14 contract pins are RETIRED. 09 Circle USDC is unchanged. Person keys 15 / 3% / 7% are replaced. Do not execute old 03. Do not queue old #1.

TravelTrust is a decentralized travel-commerce protocol. Travelers lock trip deposits in USDC escrow. TTG is for governance and Region Steward seats, not the default settlement asset for orders. Addresses follow table 1-01. Send funds only to **new** addresses listed here.

> General information only. This is not an offer of securities or virtual assets in any jurisdiction, and not investment, tax, or legal advice. Terms of service and executed agreements control.

---

## 0 · What is true now

The old stack keys are lost. The new stack is not on mainnet yet. The sale window follows the calendar, not broadcast day. Round 1 opens **2026-11-12 09:00 UTC**. There is no written production go-live.

| Fact | Now |
|------|-----|
| Old fifteen (except 09) | Lost / RETIRED |
| New fifteen mainnet broadcast | No · needs the remint broadcast passphrase |
| 08 | Empty slot this batch · not deployed |
| Public-sale window open to the public | No · even after broadcast, wait for 09:00 UTC |
| Written production go-live | No |

---

## 1 · What the protocol does

The protocol splits a travel sale into checkable on-chain paths:

- Marketplace: discovery and matching. Travel / merchant / acquisition open **only** in ten ISO countries: `CN US FR ES JP TH SG KR AU AE`
- Escrow: both parties scan to pay the deposit; traveler confirms completion, then release (guide does not sign). Mainnet settlement is USDC
- Performance bond: default 10% of order, cap 20%. Complete → back to the guide; incomplete → 100% to the traveler
- Platform fee: 5% on verified trips (taken on 11), then 12 → 13 → **04** by country. **08 is not deployed this batch**
- Region Steward: stake TTG for a seat and share that country’s real platform fees — not minted rewards
- Governance: genesis seeds the five-round calendar in the same tx. Later window/price/fee changes wait 12 hours

Merchants and guides do not stake TTG by default. Their performance uses order-side bonds, separate from steward seats.

---

## 2 · Region Steward: a different staking model

Many tokens use lock-and-emit staking to dampen sell pressure: depositors earn a low APR, often paid by inflation. TravelTrust does not.

Applying as a country’s Region Steward *is* the stake: TTG locks to the country threshold. Steward income comes from travel that already happened in that country — 45% of the platform fee to the steward’s registered wallet, 55% to the project pool (the split can be negotiated with the team and community, and reconfigured by governance proposal). With no seated steward, 100% of the platform fee goes to the pool.

TTG cannot mint after genesis, so steward pay cannot be printed as new tokens. The seat threshold is live supply × country bps / 10000, and it falls when supply is burned. A 300,000 USDC access fee goes to the operations wallet and is counted separately from the stake. It pays the founding team’s start-up costs: protocol development, security and infrastructure, early operations, and payroll. It is not a stake and does not count toward the seat threshold.

That does two jobs at once: TTG is locked in a governance seat, and the staker shares real regional flow instead of a low APR unrelated to sales.

Initial ten-country bps (of live supply): CN/US 4% (400) · FR/ES 4.5% (450) · JP/TH 2.5% (250) · SG/KR 2% (200) · AU/AE 1.5% (150). One seat per country. Steward exit: after 24×30 days you may apply; **the seat empties and the 45% cut stops that day**; the next applicant may occupy the same day; TTG returns in one shot after 90 more days. Website matches chain. The 300,000 USDC access fee is `10.payStewardAccessFee` to new 14.

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
| Public sale vault | 50% | 12.5T | New 07 PublicSaleVault `0x5Ce1f7A8a9560aFf257B184F012e87B7ee2f3A6A` |
| Governance treasury | 35% | 8.75T | Affiliate Governed DAO Treasury (admin = new 03; 03 is the door, not the vault) |
| Team | 3% | 0.75T | `0xfBe514a0863e8F8278Fe8996F8F83CCa28734A81` |
| Marketing | 5% | 1.25T | `0xee05e6BcC658D3f3900Cc1CACeBE9eef8DbB40B1` (same as 15) |
| Treasury / ops | 7% | 1.75T | `0xe3DE92DcB96396E75093A873C231Bb9Dd050346E` (same as 14) |

15 deployer/scheduler `0xee05e6BcC658D3f3900Cc1CACeBE9eef8DbB40B1` **is** the 5% bucket. 14 pause key `0xe3DE92DcB96396E75093A873C231Bb9Dd050346E` **is** the 7% bucket. Old 3% `0x010365…` / old 15 `0xe1e732…` / old 7%+14 `0xF34804…` are RETIRED.

---

## 5 · Public exchange (five short windows)

Sales run through the batch market (06) and public-sale vault (07). **Genesis seeds the batches in the same transaction** — do not wait 12 hours to seed. Buying still follows the calendar; a buy before open must fail. Pin `V9_SHORT_WINDOW_FIVE_ROUND`, about **3.905% = 976.25B**. Open **09:00 UTC** (18:00 JST). The rest of the 50% inventory stays in 07.

| Round | Open (UTC) | Close (UTC) | Window | Cap (TTG) | USDC raw per 1 TTG (6 decimals) | Plain |
|-------|------------|-------------|--------|-----------|----------------------------------|-------|
| 1 | 2026-11-12 09:00 | 2026-11-19 09:00 | 7d | 1.25B | 1 | 1 USD ≈ 1,000,000 TTG |
| 2 | 2026-12-03 09:00 | 2026-12-17 09:00 | 14d | 6.25B | 3 | |
| 3 | 2027-01-14 09:00 | 2027-02-04 09:00 | 21d | 31.25B | 5 | |
| 4 | 2027-02-25 09:00 | 2027-03-27 09:00 | 30d | 312.5B | 7 | |
| 5 | 2027-04-08 09:00 | 2027-05-23 09:00 | 45d | 625B | 9 | |

Do not republish the old long-window caps 3.75B / 18.75B / 168.75B / 2025B. Later window or price changes go through a governance vote and the 12-hour delay. Sale USDC goes to the project pool (05).

---

## 6 · Platform fee and country split

| Rule | Meaning |
|------|---------|
| Live fee path | **11 takes the cut → 12 → 13 → 04 splits by country**. 08 is empty, not the splitter |
| Platform fee rate | Default 500 bps (5%) on 11; 04 stores a mirror. Change fee = one proposal hitting 11+04; hard cap 10% |
| Seated steward | 45% to `10.feeSteward`, 55% to the project pool (must sum to 100%; governance may reconfigure) |
| No steward / exit requested that day | 100% to the project pool |
| Country key | Escrow orders carry one of the ten ISOs; unlisted codes revert |

Fees come only from verified escrow / settlement paths. There is no separate holder dividend.

---

## 7 · Merchants, guides, and the access fee

| Role | TTG stake | Performance |
|------|-----------|-------------|
| Region Steward | Active; see section 2 | Seat plus country platform-fee share |
| Merchant | Not required | Same per-order USDC bond as guides (default 10%, cap 20%) |
| Guide | TTG not required | Per-order USDC bond; optional identity stake 1000 / 5000 / 10000 USDC, not a booking gate |

The Region Steward access fee is 300,000 USDC via **10 `payStewardAccessFee`** to the **new 14 pause key** `0xe3DE92DcB96396E75093A873C231Bb9Dd050346E` (same as 7%). Do not send it to old `0xF34804…`. It funds founding start-up costs, is separate from the TTG seat stake, and is not refundable in the ordinary course.

---

## 8 · Project pool

The project pool collects sale USDC and platform-fee shares routed to the pool. Ops spend: new 02 propose → new 03 12-hour door → payee written after broadcast. Cumulative spend in any 90-day window is at most 30%. Do not send to old `0xF34804…`.

---

## 9 · Governance delay

```text
Governor  →  new 12-hour door `0xafaee79259c831630E6f7Dc5B8885E0Fbe27fb5F`
             Scheduler is an operations wallet 0xee05e6BcC658D3f3900Cc1CACeBE9eef8DbB40B1
             (not a contract; genesis 5% also lands here; not treasury)
              ├─ Market / Vault / Fee / Stake / Pool
              └─ Affiliate DAO protocolBurn
```

No multi-sig administers the 12-hour delay. Send funds only to new addresses listed on this page. Do not execute old 03 `0xF61880fe…`.

---

## 10 · Checkable addresses

| # | Name | Address | Note |
|---|------|---------|------|
| 01 | TTG | `0x01dc2706c4E0F82995d63042c06873d1DC6B3AEa` | Old `0xD5c1Ef9e…c41c9` RETIRED |
| 02 | Governor | `0xf9D9143bB632096ABeFd943D894c43C04fD16ED4` | Old #1 Canceled · do not queue |
| 03 | 12-hour delay | `0xafaee79259c831630E6f7Dc5B8885E0Fbe27fb5F` | Door, not a vault · do not execute old 03 |
| 04 | Fee router | `0x95E794B6Ed6Ce2547b22b220761De106c5f42515` | Live fee sink · reads 10 occupancy |
| 05 | Project pool | `0x55cBeD4460Ad2bCc0a9F2598af5013415B121d61` | |
| 06 | Primary market | `0xEaB632241C9c93B9012fc60a834d2D771E620130` | Seeded in genesis · buy waits for 09:00 UTC |
| 07 | Vault | `0x5Ce1f7A8a9560aFf257B184F012e87B7ee2f3A6A` | Genesis 50% · five rounds sell 3.905% |
| 08 | Empty slot | **not deployed this batch** | Number kept so 09–15 do not shift |
| 09 | USDC | `0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48` | Circle · remint does not change 09 |
| 10 | Role stake | `0x3E7C7b2238d90dea4D31A2ee397068CB2ecF1032` | Ten-country seats · 300k access fee |
| 11 | Escrow factory | `0x61c459f3fdD61a9194D23B26acA9DDC6Df9839aB` | Ten countries only · traveler confirms then release · takes 5% |
| 12 | Settlement router | `0xEe34DB838cf40b1C9b2AC2248340eFc8Ea8A1C16` | Guide does not sign payout · feeds 13/04 |
| 13 | Completion adapter | `0x4316FeC59EB5dedf66c9948E66BbBaa9d67294F0` | 11→12→13→04 |
| 14 | Pause key (person wallet) | `0xe3DE92DcB96396E75093A873C231Bb9Dd050346E` | **Also** the 7% bucket |
| 15 | Scheduler key (person wallet) | `0xee05e6BcC658D3f3900Cc1CACeBE9eef8DbB40B1` | Deployer · **also** the 5% bucket |
| 3% | Team custody | `0xfBe514a0863e8F8278Fe8996F8F83CCa28734A81` | Not table 1-01 |
| 7% | Treasury custody | `0xe3DE92DcB96396E75093A873C231Bb9Dd050346E` | Not table 1-01 · **same as 14** |

Trip money path: new 11 → 12 → 13 → 04 · USDC `0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48`. Old factory `0xcF5E02…` / old settlement `0xe5C3ED…` / old 08 FeeRouter `0xa20a2987…` HISTORICAL. Affiliate DAO `0x6fc3Be4999DE2Ad648C70e72076a66A7cB90a3c1` · Activity `0xAAc1A74d6b76405427102b602a8d7fE320f89de8` (genesis 0). Official API / Fly pins live. App / www not cut over. Written production go-live has not been issued.

---

## 11 · Security, scope, and risk

No mint after genesis. Holders cannot burn. Governance burn waits 12 hours. Platform fee starts at 5%. Pool ops spend is capped at 30% in any 90-day window. This document states living rules and checkable addresses. It does not rewrite the website or observer layer, and it does not issue go-live.

Before broadcast: new addresses are not on chain. After broadcast: genesis has already seeded; buys still follow the calendar; 08 stays empty. Regulatory, tax, and jurisdictional access are separate. Written production go-live has not been issued.

---

## Key points

- Trip deposits use USDC escrow; traveler confirms, then release. TTG is for governance and seats. Five short windows total 3.905%; round 1 opens 2026-11-12 09:00 UTC.
- Region Steward staking locks TTG; yield is that country’s real platform fee (45/55 while seated; 100% to the pool on the exit day), not inflation rewards. The 300,000 USDC access fee is a start-up cost, not a stake.
- Genesis split 50 / 35 / 3 / 5 / 7; 25 trillion supply; no mint. 08 is not deployed this batch. Live fees 11→12→13→04.
- Governance waits 12 hours. Stations 14 and 15 are person keys, not contracts.
- This page is not a securities offering and does not issue a written production go-live.

Document ID: `TTG_V9_MAINNET_EDITION_WHITEPAPER`.
