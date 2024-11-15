
---

# Fullstack Web3 Learning Repository - Step 1: Hardhat Basics

This repository is part of a larger learning journey focused on building **Fullstack Web3 applications**. In this first step, we are working with **Hardhat** to understand the basics of smart contract development and deployment on a local blockchain.

---

## 📚 **Project Overview**

### **Objective of Step 1**
- Learn the basics of **Hardhat**.
- Understand how to:
  - Write and deploy a basic smart contract.
  - Interact with a local blockchain network.
  - Use development tools like Hardhat Console and JSON-RPC.

This step sets the foundation for future steps where we will integrate frontend and backend components to build a complete dApp.

---

## 🔧 **Setup and Installation**

1. Clone the repository:
   ```bash
   git clone <repository_url>
   cd <repository_name>
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Compile the smart contracts:
   ```bash
   npx hardhat compile
   ```

---

## 📂 **Project Structure**
```
.
├── contracts          # Solidity contracts
│   └── Lock.sol       # A sample contract to lock funds until a specific time
├── scripts            # Deployment and interaction scripts
│   └── deploy.js      # Script to deploy the Lock contract
├── test               # Test files for the Lock contract
│   └── Lock.ts        # Tests for the Lock contract
├── hardhat.config.ts  # Configuration file for Hardhat
├── README.md          # Project documentation
└── artifacts          # Compiled contract artifacts (auto-generated)
```

---

## 🚀 **Step 1: Hardhat Basics**

### **1. Running a Local Blockchain**
Start a local blockchain with Hardhat:
```bash
npx hardhat node
```

- The blockchain runs on `http://127.0.0.1:8545`.
- It preloads 20 test accounts with 10,000 ETH each for development purposes.
- These accounts and private keys are visible in the console output.

### **2. Deploying the Lock Contract**
Deploy the `Lock` contract using the provided deployment script:
```bash
npx hardhat run scripts/deploy.js --network localhost
```

- The contract locks 1 ETH and sets an unlock time (e.g., 5 minutes from now).
- The console displays:
  - The contract's address.
  - The unlock time.

### **3. Interacting with the Contract**
Open the Hardhat console to interact with the deployed contract:
```bash
npx hardhat console --network localhost
```

#### Example Commands:
```javascript
// Attach to the deployed contract
const lockAddress = "deployed_contract_address"; // Replace with your contract address
const Lock = await ethers.getContractFactory("Lock");
const lock = await Lock.attach(lockAddress);

// Check unlock time
const unlockTime = await lock.unlockTime();
console.log(`Unlock time: ${unlockTime}`);

// Attempt withdrawal (if time has passed)
await lock.withdraw();
```

---

## 📘 **The Lock Contract**

The `Lock` contract allows locking funds until a specific unlock time. Only the owner of the contract can withdraw the funds after the unlock time has passed.

### **Key Features:**
1. **Constructor**:
   - Sets the unlock time and assigns the owner of the contract.
2. **withdraw()**:
   - Ensures that only the owner can withdraw the funds.
   - Requires the current time to be greater than or equal to the unlock time.
   - Emits an event with the withdrawal details.

---

## 🛠 **Key Commands**
Here are the key Hardhat commands used in this step:

- **Compile contracts**:
  ```bash
  npx hardhat compile
  ```

- **Run tests**:
  ```bash
  npx hardhat test
  ```

- **Start local blockchain**:
  ```bash
  npx hardhat node
  ```

- **Deploy contracts**:
  ```bash
  npx hardhat run scripts/deploy.js --network localhost
  ```

- **Interact with the console**:
  ```bash
  npx hardhat console --network localhost
  ```

---

## 🌟 **Next Steps**

- Explore the `Lock` contract's logic further.
- Understand how to write more complex smart contracts.
- Prepare for the next step, where we will integrate the smart contract with a frontend application using **React.js** and **ethers.js**.

---

This is **Step 1** of a larger Fullstack Web3 learning project. Each step builds upon the previous one to create a complete decentralized application (dApp).

--- 
# blockchain_web3
