# 💰 FundMe – Decentralized Crowdfunding on Ethereum

A secure, minimalistic, and trustless crowdfunding smart contract built with **Solidity** and powered by **Chainlink** price feeds.  
Allows users to fund with ETH validated in USD, and only the contract owner can withdraw the funds securely.

> 🔐 Designed for transparency, decentralization, and optimal gas efficiency.

---

## 🌍 Overview

- **Language:** Solidity `^0.8.18`  
- **Framework:** [Foundry](https://book.getfoundry.sh/) – (Forge, Cast, Anvil)  
- **Networks:** Ethereum Testnets, zkSync-compatible chains  
- **Oracle Integration:** [Chainlink](https://chain.link) ETH/USD Price Feeds  
- **Goal:** Enforce fair funding logic via real-time USD value checks and secure ownership-based withdrawal.

---

## ✨ Key Features

- ✅ **Minimum Contribution Threshold** – Ensures users contribute at least $5 (USD) worth of ETH.
- ✅ **Live Chainlink Oracles** – Fetches accurate, real-time ETH/USD rates for price validation.
- ✅ **Owner-Only Withdrawals** – Only the contract deployer can retrieve funds, ensuring control.
- ✅ **Modular Design** – Separation of logic via `PriceConverter` library.
- ✅ **Optimized for Gas** – Implements `constant`, `immutable`, and low-level error handling.
- ✅ **Robust Access Control** – Uses custom errors and modifiers for strict permissions.

---

## 🧠 Contract Architecture
```
📁 src/
├── FundMe.sol            # Main smart contract for funding logic
└── PriceConverter.sol    # Library for ETH to USD conversion

📁 script/
├── DeployFundMe.s.sol    # Automated deployment script
├── HelperConfig.s.sol    # Environment/network configuration
└── Interactions.s.sol    # Scripts for interacting with deployed contract

📁 test/
└── FundMeTest.t.sol      # Unit and integration tests (Forge)
```

---


## 🛡️ Security Considerations

- 🔒 **Access Control (`onlyOwner`)** – Restricts withdrawal functionality to the original deployer.
- 🧾 **Custom Errors** – Uses `FundMe__NotOwner` to reduce gas vs string-based errors.
- 💸 **Dynamic Price Enforcement** – Prevents underfunding via Chainlink-based real-time ETH/USD checks.
- 🧩 **Code Separation** – Price logic is decoupled from main contract, improving testability and reuse.

---

## 📄 License

Licensed under the **MIT License**.  
Feel free to use, modify, or build upon this project in your own decentralized applications.

---

## 🚀 Getting Started

To clone and run the project locally:

```bash
git clone https://github.com/EmadXYZ/FundMe.git
cd FundMe
forge install
forge build
forge test
