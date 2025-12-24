# Opal Riverline (Built for Base)

Opal Riverline is a compact Base-focused workspace designed to validate Base network identity and observe public onchain data through non-invasive, read-only interactions.

---

## Why this repository exists

This project serves as a practical reference for developers who want to:
- Confirm Base RPC availability and correctness  
- Inspect balances, blocks, and basic account state  
- Cross-check results using Basescan  
- Experiment with Base tooling without sending transactions  

The emphasis is on transparency and verifiability.

---

## Base networks in scope

Base Sepolia  
chainId (decimal): 84532  
Explorer: https://sepolia.basescan.org  

Base Mainnet  
chainId (decimal): 8453  
Explorer: https://basescan.org  

---

## Repository layout

- app/opal-riverline.ts  
  Browser-based script that connects a Coinbase Wallet and performs read-only Base RPC queries.

- config/base.networks.json  
  Static configuration describing Base networks, RPC endpoints, and explorer URLs.

- docs/architecture.md  
  Notes explaining the read-only design, Base alignment, and dependency choices.

- docs/validation-notes.md  
  Chronological record of Base Sepolia validation steps and explorer checks.

- scripts/sample-addresses.json  
  Example addresses used for repeatable inspection during testing.

- contracts/  
  Solidity contracts deployed to Base Sepolia for testnet validation:
  - structs.sol — improves code readability and organization 
  - storage.sol — saves and retrieves data between transactions 
  - inheritance.sol — reuses logic and state from parent contracts

- package.json  
  Dependency manifest referencing Coinbase SDKs and multiple Base and Coinbase repositories.

- README.md  
  Primary technical documentation.

---

## What the script does

Once loaded in a browser, the script allows you to:
- Connect a Coinbase Wallet via EIP-1193  
- Validate the active Base chainId  
- Retrieve ETH balances and transaction counts  
- Inspect the latest block and gas signals  
- Follow Basescan links for independent confirmation  

All functionality is strictly read-only.

---
## Testnet Deployment (Base Sepolia)

As part of pre-production validation, one or more contracts may be deployed to the Base Sepolia test network to confirm correct behavior and tooling compatibility.

Network: Base Sepolia  
chainId (decimal): 84532  
Explorer: https://sepolia.basescan.org  

Contract storage.sol address:  
0x8720783a0d23B111dc9686d92e1328eAe7064901 

Deployment and verification:
- https://sepolia.basescan.org/address/0x8720783a0d23B111dc9686d92e1328eAe7064901 
- https://sepolia.basescan.org/0x8720783a0d23B111dc9686d92e1328eAe7064901 /0#code  

Contract structs.sol address:  
0x68fC62849DD5C7065733944490093c0ACE64813D 

Deployment and verification:
- https://sepolia.basescan.org/address/0x68fC62849DD5C7065733944490093c0ACE64813D 
- https://sepolia.basescan.org/0x68fC62849DD5C7065733944490093c0ACE64813D /0#code  

Contract inheritance.sol address:  
0xb8871e9bf61B03720b46A6103ceDC796d50b9823

Deployment and verification:
- https://sepolia.basescan.org/address/0xb8871e9bf61B03720b46A6103ceDC796d50b9823
- https://sepolia.basescan.org/0xb8871e9bf61B03720b46A6103ceDC796d50b9823/0#code  

These testnet deployments provide a controlled environment for validating Base tooling, account abstraction flows, and read-only onchain interactions prior to Base Mainnet usage

## Tooling and ecosystem references

This repository intentionally pulls from the Base and Coinbase ecosystems:
- Coinbase Wallet SDK for wallet connectivity  
- OnchainKit references for Base-native patterns  
- viem for efficient, typed RPC access  
- Multiple Base and Coinbase GitHub repositories included as dependencies  

---

## License

MIT License

Copyright (c) 2025 YOUR_NAME

---

## Author

GitHub: https://github.com/opal-riverline

Email: basest_selves.0a@icloud.com

Public contact: https://x.com/Elmira91428747 

---
