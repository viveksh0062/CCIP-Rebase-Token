Ccip Rebase Token Readme
🚀 CCIP Rebase Token

A fully cross-chain Rebase Token System built using OpenZeppelin, Chainlink CCIP, and a custom RebaseTokenPool. This project demonstrates how to build, manage, and transfer a rebasing token across chains using Chainlink CCIP (Cross-Chain Interoperability Protocol).

This repository is designed with clarity, modularity, and testability in mind, following advanced Foundry and Solidity best practices.

📌 Features

Cross-chain transfers using Chainlink CCIP

Rebasing token mechanism with supply adjustments

Custom Token Pool using CCIP TokenPool

Secure token accounting via Vault contract

Upgradeable architecture ready (modular, interface-driven)

Complete Foundry Test Suite (unit + cross-chain simulations)

Deployment scripts using Foundry Scripts

📁 Project Structure
CCIP-Rebase-Token/
│
├── script/
│   ├── BridgeToken.s.sol        # Sends token across chains using CCIP
│   ├── ConfigurePool.s.sol      # Sets up rebase pool / CCIP configuration
│   └── Deployer.s.sol           # Deploys all contracts with correct wiring
│
├── src/
│   ├── interfaces/
│   │   └── IRebaseToken.sol     # Interface for rebase token
│   │
│   ├── RebaseToken.sol          # Rebasing ERC20 token
│   ├── RebaseTokenPool.sol      # CCIP TokenPool for cross-chain transfers
│   └── Vault.sol                # Handles supply + accounting logic
│
├── test/
│   ├── CrossChain.t.sol         # Cross-chain messaging tests
│   └── RebaseToken.t.sol        # Unit tests for local rebase logic
│
└── README.md
🧱 Core Contracts
1️⃣ RebaseToken.sol

A rebasing ERC20 token implementing:

Elastic supply

Scalable balances

Rebase multiplier logic

Only Vault can trigger rebases

2️⃣ RebaseTokenPool.sol

Custom CCIP TokenPool implementation that:

Encodes/decodes messages

Handles mint/burn on remote chains

Integrates with CCIP Router

Ensures consistent supply across networks

3️⃣ Vault.sol

Handles:

Global supply logic

Rebase factor updates

Accounting for user balances

Secure access control

🔗 CCIP Integration

The project uses:

IAny2EVMMessage for receiving cross-chain messages

EVM2AnyMessage for sending tokens across chains

CCIP Router for message dispatch

Custom Pool to handle token movement

End-to-end CCIP operations tested in CrossChain.t.sol.

🛠 Deployment Scripts
Deployer.s.sol

Deploys:

RebaseToken

Vault

RebaseTokenPool

CCIP Router configuration

ConfigurePool.s.sol

Sets up:

TokenPool configuration

Chain selectors

Admin roles

BridgeToken.s.sol

Sends cross-chain messages using:

Client.EVM2AnyMessage

Token metadata encoding

Token transfer through CCIP

🧪 Testing

Tests are written using Foundry.

✔ RebaseToken.t.sol

balance scaling

rebase factor updates

supply correctness

✔ CrossChain.t.sol

CCIP message formatting

Pool encoding/decoding

Cross-chain mint/burn simulation

Run all tests:

forge test -vvvv
🚀 Getting Started

Install dependencies:

forge install

Build the project:

forge build

Run deployment:

forge script script/Deployer.s.sol --rpc-url <RPC> --broadcast
📡 Environment Variables

Create a .env file:

PRIVATE_KEY=
SOURCE_CHAIN_RPC=
DEST_CHAIN_RPC=
CCIP_ROUTER=
TOKEN_ADMIN=
🧭 Future Improvements

Add rebase history events

Add graphical dashboard for CCIP flow

Add multi-chain reward logic

Deploy on Sepolia, Mumbai, Arbitrum testnets

👤 Author
Vivek Sharma

X (Twitter): https://x.com/viveksh0062

LinkedIn: https://www.linkedin.com/in/vivek-sharma-679606360/

Discord: viveksh0062

⭐ Support

If you like the project, consider giving a star ⭐ on GitHub!

📜 License

MIT License — free to use and modify.