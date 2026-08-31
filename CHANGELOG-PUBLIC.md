# Public changelog (documentation pack)

## 2026-08-31 — wave 1.1 quality pass

- Fixed all internal navigation dead links (removed Wave 2-only pages from hubs)
- Sanitized private `runbook/` / `registry/` / `scripts/` links from exported markdown
- Added [GLOSSARY.md](GLOSSARY.md) · GitHub About metadata doc
- SECURITY.md points to CONTACT.md only
- Governance: explicit **48h Mainnet** vs **12h Sepolia** timelock note
- Export gate: `DEAD_LINKS=0` required

## 2026-08-22 — wave 1 initial export

- Documentation-only public repository created
- English / Chinese doc hubs, governance, tokenomics, whitepapers
- Sepolia TESTNET address disclosure (`docs/deployments/sepolia.md`)
- Logo assets under `assets/logo/`
- **Excluded:** Solidity source, API, frontend, scripts, internal evidence
- **Deferred:** `docs/deployments/mainnet.md`, Etherscan verified links pack, final Mainnet registry (after V9 Mainnet Reality)
