# Audit-Guard: Blockchain-Integrated Corporate Audit System

VeriChain-Audit is a robust, transparent, and immutable audit management system designed to bridge the "Integrity Gap" in traditional auditing. By leveraging a **Dual-Layer Hash Validation Framework (DLH-VF)**, the system synchronizes off-chain database records (MySQL/MongoDB) with on-chain cryptographic proofs (Ethereum Blockchain).

## Key Features

- **Dual-Layer Hash Validation (DLH-VF):** Synchronizes `Record_Hash` (data fingerprint) and `Blockchain_TX` (transaction reference) for deep verification.
- **Hybrid Anchor Storage:** Optimized performance by storing only cryptographic fingerprints on-chain while keeping large datasets in high-performance local databases.
- **Proactive Tamper Detection:** Real-time integrity scanning that identifies discrepancies between local data and blockchain anchors.
- **Closed-Loop Correction Workflow:** Automated administrative tools to flag tampered records and trigger mandatory correction cycles.
- **Multi-Role Orchestration:** Dedicated dashboards and workflows for **Admins**, **Auditors**, and **Business Users**.

## Technology Stack

- **Backend:** Node.js, Express.js
- **Databases:** MySQL (Relational data), MongoDB (NoSQL logs & evidence)
- **Blockchain:** Web3.js, Ethereum Smart Contracts (Solidity)
- **Real-time:** Socket.io for live integrity alerts
- **Security:** SHA-256 Hashing, Bcrypt encryption

## System Architecture

The system operates on a hybrid model:
1.  **Data Layer:** Records are initially stored in MySQL and MongoDB.
2.  **Hashing Layer:** A unique SHA-256 fingerprint is generated for every critical action.
3.  **Anchor Layer:** The fingerprint is anchored to the Ethereum blockchain via a smart contract.
4.  **Verification Layer:** The system periodically scans the databases and compares current hashes against the on-chain "Source of Truth."

## Getting Started

### Prerequisites
- Node.js (v16+)
- MySQL Server
- MongoDB Instance
- Ethereum Provider (e.g., Ganache, Infura, or Alchemy)

### Installation
1. Clone the repository:
   ```bash
   git clone [https://github.com/yourusername/VeriChain-Audit.git](https://github.com/yourusername/VeriChain-Audit.git)

2. Install dependencies:
   ```bash
   npm install

3. Configure Environment: Create a .env file in the root directory and add your credentials:

DB_HOST=localhost
DB_USER=root
DB_PASS=yourpassword
MONGO_URI=mongodb://localhost:27010/audit
BLOCKCHAIN_NODE_URL=...
PRIVATE_KEY=...
CONTRACT_ADDRESS=...

4. Run the application:
   ```bash
   npm start
   
👥 Roles & Workflows
Business User: Uploads records and evidence.
Admin: Manages users, reviews discrepancy alerts, and initiates correction loops.
Auditor: Performs deep integrity scans and provides human-in-the-loop validation of blockchain proofs.
