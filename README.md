# 🧾 FundMe.sol

## About

Welcome to **FundMe** – a simple smart contract where users can fund in ETH, but only if the value of their ETH is greater than $5 USD!  
The contract uses **Chainlink price feeds** to check the ETH/USD rate in real time.  
Only the owner (contract deployer) can withdraw the funds, and we've even optimized the withdrawal function for lower gas costs.  
It's lightweight, testable, and designed with security in mind!

---

## 🚀 Getting Started

### - Requirements

#### -- `git`  
You'll know you did it right if you can run:
```bash
git --version
```
And you see a response like:
```
git version x.x.x
```

#### -- `foundry`  
You'll know you did it right if you can run:
```bash
forge --version
```
And you see a response like:
```
forge 0.2.0 (816e00b 2023-03-16T00:05:26.396218Z)
```

---

### - Quickstart

```bash
git clone https://github.com/YourUsername/fundme-foundry
cd fundme-foundry
make
```

This will install dependencies and get everything ready for development.

---

## ⚒️ Usage

### - Deploy

To deploy locally or to a network (like Sepolia):

```bash
forge script script/DeployFundMe.s.sol --rpc-url $SEPOLIA_RPC_URL --broadcast
```

Make sure to set your `.env` with:

```env
SEPOLIA_RPC_URL=https://sepolia.infura.io/v3/your-api-key
PRIVATE_KEY=your-private-key
ETHERSCAN_API_KEY=your-etherscan-key
```

---

### - Testing

Run tests with:

```bash
forge test -vv
```

This project includes:

- ✅ Unit tests for funding
- ✅ Withdrawal by owner
- ✅ Mock price feed for local testing

#### -- Test Coverage

To check gas costs:

```bash
forge snapshot
```

Or to generate a gas report automatically:

```bash
forge test --gas-report
```

---

## 🌍 Deployment to a testnet or mainnet

### - Scripts

Deployment is handled via `script/DeployFundMe.s.sol` using the `HelperConfig` to dynamically pick the right price feed for:

- Local (Anvil)
- Sepolia
- Mainnet

You can customize it for your own RPC setup.

---

### - Withdraw

Only the contract owner can call:

```solidity
withdraw()
cheaperWithdraw() // more gas efficient
```

---

### - Estimate Gas

Want to check how much gas is used for a function?

```bash
forge test --gas-report
```

---

## 📌 Formatting

This project follows:

- **Solidity style guide**
- `forge fmt` for formatting
- Consistent naming with `s_`, `i_`, and `constant` identifiers

To format:

```bash
forge fmt
```

---

## 🧠 Additional Info

- Chainlink ETH/USD price feeds for Sepolia: `0x694AA1769357215DE4FAC081bf1f309aDC325306`
- Optimized for Foundry scripting and testing workflows
- Mocks included for fast local testing

---

## 🙏 Thank You!

This project was inspired by the [Cyfrin Updraft](https://github.com/Cyfrin/updraft) course and built with ❤️ by [TheMilenkov](https://github.com/TheMilenkov).

Feel free to fork, test, and deploy. If you liked it — give it a ⭐ on GitHub!
