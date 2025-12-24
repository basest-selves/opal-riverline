# Opal Riverline — Validation Notes

Chronological record of Base Sepolia validation steps and explorer checks.

---

## 2025-12-24 — Initial Sepolia Validation

**Target network:** Base Sepolia  
**Chain ID:** 84532  
**RPC:** https://sepolia.base.org  
**Explorer:** https://sepolia.basescan.org

### Step 1 — Config sanity
- [ ] Confirm `config/base.networks.json` includes `base-sepolia`
- [ ] Verify `chainId` is `84532`
- [ ] Confirm explorer base URL is `https://sepolia.basescan.org`

### Step 2 — RPC connectivity
- [ ] Fetch latest block number (should be > 0)
- [ ] Re-fetch after a short pause and confirm it can advance
- [ ] If issues, switch to a fallback RPC and re-check

### Step 3 — Read-only inspection
Using `scripts/sample-addresses.json`:

- [ ] Get ETH balance for `exampleEOA`
- [ ] Get code for `exampleContract` (should be `0x` for non-contracts)
- [ ] Confirm zero address returns safe values (no crashes)
- [ ] Confirm burn address resolves (no crashes)

### Step 4 — Explorer verification
- [ ] Open `exampleEOA` on Sepolia BaseScan
- [ ] Open latest block on Sepolia BaseScan
- [ ] Ensure no mainnet BaseScan links are used during testnet runs

### Notes
- Treat chainId/RPC changes as high-risk.
- Prefer fixing config before modifying logic.

---
