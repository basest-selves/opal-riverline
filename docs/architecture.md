# Opal Riverline — Architecture Notes

Notes explaining the read-only design, Base alignment, and dependency choices.

---

## Read-only Design

Opal Riverline is intentionally **read-only first**:

- Native balance checks
- Contract-code presence checks
- Block / chain metadata reads
- Token metadata reads (symbol / decimals) when applicable

This keeps risk low and validation repeatable.

---

## Base Alignment

The project is Base-first by design:

- Supported networks are limited to:
  - Base Mainnet (`8453`)
  - Base Sepolia (`84532`)
- RPC endpoints are public and defined in `config/base.networks.json`
- Explorer links are derived from config (BaseScan domains)
- No hardcoded chain IDs or explorer URLs in source logic

---

## Dependency Choices

Guidelines used for dependencies:

- Prefer Base ecosystem packages when possible
- Keep the set small and justified
- Avoid overlapping libraries that solve the same job
- Treat network metadata as configuration, not code

If a dependency is added, document:
- what capability it provides
- why it is needed now
- what the fallback plan is (removal/replacement)

---

## Design Tradeoffs

- Pros:
  - Simple, auditable behavior
  - Easy to validate on testnet
  - Minimal external risk surface

- Cons:
  - No transaction execution paths
  - Less coverage for write-side edge cases

These are acceptable for the current scope.

---

_Last updated: initial scaffold_
