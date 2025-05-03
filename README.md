💰 FundMe – A Decentralized Crowdfunding Smart Contract  
Empowering secure, trustless fundraising directly on the Ethereum blockchain. Contributors send ETH, and only the contract owner can withdraw once conditions are met.

🔐 Transparent funding powered by Chainlink price feeds and Solidity.

📦 Overview  
Language: Solidity (^0.8.18)  
Tooling: Foundry (Forge, Anvil, Cast)  
Network: Configurable (supports testnets & zkSync-compatible chains)  
Purpose: A decentralized and programmable crowdfunding contract where users can fund in ETH, validated against USD value via Chainlink oracles.

✨ Key Features  
✅ USD-based Funding Threshold – Users must contribute a minimum of $5 (USD) worth of ETH.  
✅ Chainlink Price Feeds – Real-time ETH/USD rate fetched from trusted oracles.  
✅ Withdrawal by Owner – Only the contract deployer (owner) can withdraw funds.  
✅ Access Control – Secure access with custom error handling and modifiers.  
✅ Modular Architecture – Includes helper scripts and price conversion logic in a separate library.  
✅ Gas Optimization – Uses constants, immutables, and efficient mappings.

🛠 Structure  
📁 `src/` – Contains main contract `FundMe.sol` and `PriceConverter.sol` library  
📁 `script/` – Deployment and interaction scripts  
📁 `test/` – Unit and integration tests written using Foundry's Forge  
🧪 `foundry.toml` – Configuration file for the Foundry framework  

🔐 Security Considerations  
✔️ OnlyOwner Modifier – Ensures only the contract creator can call sensitive functions.  
✔️ Custom Error (`FundMe__NotOwner`) – Reduces gas usage compared to string errors.  
✔️ Safe Value Checks – Prevents underfunding via real-time conversion and strict `require` statements.  
✔️ Separation of Concerns – Price conversion handled in a dedicated library, reducing code repetition.  

🧾 License  
This project is licensed under the MIT License – free to use, modify, and share.

🚀 Contributions are welcome – Fork it, test it, and submit your PRs!

📥 Clone & Use  
```bash
git clone https://github.com/yourusername/FundMe.git
cd FundMe
forge build
forge test
