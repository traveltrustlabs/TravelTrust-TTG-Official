# TravelTrust · TTG V9 — Official Public Documentation

**Repository type:** documentation-only · **no smart contract source code**  
**Design Lock:** DL_R1 · Candidate `V9_AUDIT_CANDIDATE_DESIGN_LOCK`  
**`TT_PRODUCTION_GO`:** NO_GO  

## Three truth planes (do not mix)

```text
Private monorepo     → implementation & internal SSOT (not public)
This GitHub repo     → filtered official docs for investors / reviewers
Etherscan / chain    → verified bytecode & deployed contract facts
```

Smart contract **source will be verified on Etherscan** for finalized Mainnet deployments — it is **not** published in this repository until that cutover is complete.

## TravelTrust in one paragraph

TravelTrust is a decentralized travel-commerce protocol: marketplace matching, on-chain Escrow for user principal (USDC), and V9 governance / fee / sale / stake modules under Design Lock **DL_R1**.

**TTG** is the governance token (25T genesis · **NO-MINT** after). It is **not** the default settlement asset for travel orders.

> **“Mainnet Edition” whitepaper** names the target protocol edition — **not** a claim that V9 is fully live on Mainnet today. See [GLOSSARY.md](GLOSSARY.md).

## Documentation map

| | |
|--|--|
| English hub | [docs/en/README.md](docs/en/README.md) |
| 中文入口 | [docs/zh/README.md](docs/zh/README.md) |
| Whitepaper (EN) | [docs/whitepaper/TT-TTG-V9-MAINNET-EDITION-WHITEPAPER-EN-LATEST.md](docs/whitepaper/TT-TTG-V9-MAINNET-EDITION-WHITEPAPER-EN-LATEST.md) |
| 白皮书（中文） | [docs/whitepaper/TT-TTG-V9-MAINNET-EDITION-WHITEPAPER-LATEST.md](docs/whitepaper/TT-TTG-V9-MAINNET-EDITION-WHITEPAPER-LATEST.md) |
| Governance | [docs/governance/](docs/governance/) |
| Tokenomics | [docs/tokenomics/](docs/tokenomics/) |
| Sepolia (TESTNET) | [docs/deployments/sepolia.md](docs/deployments/sepolia.md) |
| Contact | [CONTACT.md](CONTACT.md) |
| Security | [SECURITY.md](SECURITY.md) |
| Glossary | [GLOSSARY.md](GLOSSARY.md) |

## Deployment status (public)

| Network | Status in this repo |
|---------|---------------------|
| **Sepolia** | [TESTNET / V9_TARGET](docs/deployments/sepolia.md) — rehearsal in progress |
| **Mainnet** | **Wave 2** — `docs/deployments/mainnet.md` after V9 Mainnet Reality |

## Official links

| | |
|--|--|
| Website | https://www.web3-ttg.com |
| Contact | traveltrust.ir@gmail.com |
| System mail (OTP only) | noreply@web3-ttg.com — not for human support |

## Disclaimer

Not investment advice. Smart contracts involve risk of loss. Historical V8 / Remint / R2_FINAL paths are **LEGACY** — see [docs/en/Legacy-Policy.md](docs/en/Legacy-Policy.md).

---

*Wave 1.1 public export · documentation only · does not replace on-chain truth.*
