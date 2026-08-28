# TravelTrust · TTG V9 — Official Public Documentation

**Repository:** https://github.com/traveltrustlabs/TravelTrust-TTG-Official  
**Repository type:** documentation-only · **no smart contract source code**  
**Nature:** **external public docs** (not the private engineering monorepo)  
**Design Lock:** DL_R1 · Candidate `V9_AUDIT_CANDIDATE_DESIGN_LOCK`  
**`TT_PRODUCTION_GO`:** NO_GO  

## Three truth planes (do not mix)

```text
Private monorepo (internal)  → implementation & internal SSOT
This GitHub repo (external)  → filtered official docs
Etherscan / chain            → verified bytecode & deployed facts
```

## TravelTrust in one paragraph

TravelTrust is a decentralized travel-commerce protocol: marketplace matching, on-chain Escrow for user principal (USDC), and V9 governance / fee / sale / stake modules under Design Lock **DL_R1**.

**TTG** is the governance token (25T genesis · **NO-MINT** after). It is **not** the default settlement asset for travel orders.

> **“Mainnet Edition” whitepaper** names the target protocol edition — **not** a claim that V9 is fully live on Mainnet today. See [GLOSSARY.md](GLOSSARY.md).

## Web3 release notes

Public exchange is **five short windows** (about 3.905% of 25T). Schedule pin `V9_SHORT_WINDOW_FIVE_ROUND` executed 2026-08-26. **Windows are not open.** Official primary-market / Vault Timelock delay is **12 hours** (Phase1 48h SoloTimelock is LEGACY). See [docs/RELEASE-NOTES.md](docs/RELEASE-NOTES.md).

## Documentation map

| | |
|--|--|
| English hub | [docs/en/README.md](docs/en/README.md) |
| 中文入口 | [docs/zh/README.md](docs/zh/README.md) |
| Release notes | [docs/RELEASE-NOTES.md](docs/RELEASE-NOTES.md) |
| Whitepaper (EN) | [docs/whitepaper/TT-TTG-V9-MAINNET-EDITION-WHITEPAPER-EN-LATEST.md](docs/whitepaper/TT-TTG-V9-MAINNET-EDITION-WHITEPAPER-EN-LATEST.md) |
| 白皮书（中文） | [docs/whitepaper/TT-TTG-V9-MAINNET-EDITION-WHITEPAPER-LATEST.md](docs/whitepaper/TT-TTG-V9-MAINNET-EDITION-WHITEPAPER-LATEST.md) |
| Primary Market | [docs/en/Primary-Market.md](docs/en/Primary-Market.md) |
| Mainnet Phase1 | [docs/en/Mainnet-Deployments.md](docs/en/Mainnet-Deployments.md) |
| Contract Registry | [docs/en/Contract-Registry.md](docs/en/Contract-Registry.md) |
| Governance | [docs/governance/](docs/governance/) |
| Tokenomics | [docs/tokenomics/](docs/tokenomics/) |
| Sepolia (TESTNET) | [docs/deployments/sepolia.md](docs/deployments/sepolia.md) |
| Contact | [CONTACT.md](CONTACT.md) |
| Security | [SECURITY.md](SECURITY.md) |
| Glossary | [GLOSSARY.md](GLOSSARY.md) |

## Deployment status (public)

| Network | Status in this repo |
|---------|---------------------|
| **Sepolia** | [TESTNET / V9_TARGET](docs/deployments/sepolia.md) |
| **Mainnet** | Phase1 addresses disclosed as `DEPLOYED_PENDING_CUTOVER` · **≠** Fully Active · Etherscan verified-source pack = Wave 2 |

## Official links

| | |
|--|--|
| Website | https://www.web3-ttg.com |
| This repo | https://github.com/traveltrustlabs/TravelTrust-TTG-Official |
| Contact | traveltrust.ir@gmail.com |
| System mail (OTP only) | noreply@web3-ttg.com — not for human support |

## Disclaimer

Not investment advice. Smart contracts involve risk of loss. Historical V8 / Remint / R2_FINAL paths are **LEGACY** — see [docs/en/Legacy-Policy.md](docs/en/Legacy-Policy.md).

---

*Wave 1.2 public export · documentation only · does not replace on-chain truth.*
