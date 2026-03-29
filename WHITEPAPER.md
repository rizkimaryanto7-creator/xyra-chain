# THE XYRA CHAIN (xyra-2) PROTOCOL
## A Sovereign Multi-Chain Infrastructure for Global Scalability and Decentralized Autonomy

**Document Status:** Official Technical Release (v1.2.0)
**Network ID:** xyra-2
**Native Asset:** Xyrium (XYRA)
**Core Architect:** XYRA Team (Rizki Maryanto)
**Year:** 2026

---

## 1. EXECUTIVE SUMMARY
Xyra Chain is a high-performance Layer-1 blockchain protocol engineered to bridge the gap between application sovereignty and shared security. Leveraging the Cosmos SDK and the CometBFT consensus engine, Chain id : Xyra-2 introduces a sovereign architecture that enables instant finality, near-zero gas fees, and seamless cross-chain interoperability. The protocol’s vision is to establish the foundation for the future internet economy through equitable token distribution and resilient node infrastructure.

---

## 2. PHILOSOPHY & PROTOCOL VISION

### 2.1 The Traditional Scalability Bottleneck
First and second-generation blockchains suffer from throughput limitations and unpredictable gas costs. Xyra-2 eliminates these barriers by decoupling application logic from consensus logic, enabling maximum efficiency across every layer of the stack.

### 2.2 Sovereignty Without Isolation
Xyra Chain is built on the belief in a multi-chain future. Through the IBC (Inter-Blockchain Communication) protocol, Xyra-2 does not exist in a vacuum; it serves as a vital hub for value and data exchange across the entire Interchain ecosystem.

---

## 3. ARCHITECTURAL DEEP-DIVE: CONSENSUS & SECURITY

### 3.1 CometBFT: Finite State Machine & BFT Consensus
Xyra-2 operates on the CometBFT consensus engine, a Byzantine Fault Tolerant (BFT) implementation that separates the application from consensus via the ABCI (Application BlockChain Interface).

* **Proposer Selection:** The block proposer selection is handled via a weighted round-robin mechanism, where a validator’s probability of being selected is directly proportional to their **Voting Power** (staked XYRA).
* **The Three-Step Consensus Process:**
    1. **Pre-vote:** Validators receive a block proposal and validate the data structure. If valid, they broadcast a pre-vote message.
    2. **Pre-commit:** If a validator receives >2/3 pre-votes for the same block, they broadcast a pre-commit.
    3. **Commit:** Upon receiving >2/3 pre-commits, the block is considered cryptographically committed to the ledger. This ensures **Instant Finality** without the risk of chain-splits or re-orgs.

### 3.2 Slashing Algorithms & Network Resilience
To safeguard the 108M XYRA economic integrity, Xyra-2 implements strict automated penalty protocols (Slashing) via the `x/slashing` and `x/staking` modules.

#### A. Liveness Fault (Downtime Slashing)
Validators are required to maintain high node uptime. Failure to sign blocks within a specific window triggers:
* **Threshold:** Missing more than 50% of blocks within the last 10,000 blocks (sliding window).
* **Penalty:** A 1% deduction from the total staked balance.
* **Jailing:** The validator is removed from the active set (Jailed) for a minimum of 10 minutes and must manually submit an `unjail` transaction after resolving technical issues.

#### B. Double-Sign Fault (Equivocation Slashing)
A critical violation where a validator signs two different blocks at the same height.
* **Detection:** The protocol detects cryptographic evidence of conflicting pre-commit messages.
* **Penalty:** A severe 5.0% deduction from the total balance (including delegator funds).
* **Permanent Ban:** The validator is **Tombstoned** (permanently removed from the set) and cannot re-enter the network.

---

## 4. CRYPTOGRAPHIC PRIMITIVES & DATA INTEGRITY

### 4.1 Ed25519 & Secp256k1
Xyra-2 utilizes a dual elliptic curve standard for maximum security:
* **Ed25519:** Used for Consensus Signing (Validator keys) due to its high-speed batch signature verification.
* **Secp256k1:** Used for user accounts to ensure full compatibility with the existing hardware wallet ecosystem (e.g., Ledger).

### 4.2 IAVL+ Tree & State Merkleization
Every state transition in Xyra-2 is stored in an IAVL+ Tree, a balanced binary tree structure that enables:
* **Proof Generation:** Users can verify balances using only a root hash (supporting Light Clients).
* **Fast Sync:** New nodes can synchronize data efficiently through state snapshots. 

---

## 5. NODE INFRASTRUCTURE & VALIDATORS

### 5.1 The Three-Pillar Validator Architecture
The early-stage security of Xyra-2 is sustained by three core validator entities, professionally managed to guarantee 99.9% network availability:
1. **XYRA-CHAIN (The Guardian):** The primary protocol node serving as the anchor for network state synchronization and the lead data provider for explorers.
2. **VOID-BREAKER (The Shield):** A high-redundancy node equipped with multi-layered anti-DDoS protection, ensuring network stability during extreme traffic surges.
3. **PAPERLINE (The Engine):** A high-performance optimized node focused on parallel transaction processing to maintain maximum throughput.

### 5.2 Connectivity & Public Access
Xyra-2 provides official endpoints supporting gRPC, RPC, and REST API protocols to facilitate seamless developer integration:
* **RPC Endpoint:** `https://rpc.xyra-mainnet.org`
* **API Endpoint:** `https://api.xyra-mainnet.org`
* **Block Time:** Consistently maintained at **~5.0 seconds**, providing a responsive user experience with Near-Instant Confirmation.

---

## 6. TOKEN ECONOMICS (TOKENOMICS)

### 6.1 Supply & Inflation Dynamics
* **Total Genesis Supply:** 108,000,000 XYRA.
* **Target Inflation Rate:** **13% Annually**.
* **Dynamic Inflation Logic:** Xyra-2 utilizes a dynamic algorithm based on the **Bonding Ratio**. If the total staked XYRA falls below 67%, inflation gradually increases (up to +3%) to incentivize network security. Conversely, if staking exceeds the target, inflation scales down to preserve asset scarcity.

### 6.2 Token Distribution Allocation (Fixed Cap)
The distribution of 108 Million XYRA tokens is strategically designed to balance community incentives, technical development, and infrastructural sustainability:

| Allocation Category | Token Amount (XYRA) | Percentage | Purpose & Vesting |
| :--- | :--- | :--- | :--- |
| **Community & Ecosystem** | 40,000,000 | 37.04% | Airdrops, Staking Rewards, & Community Pool. |
| **Fundraiser & Partners** | 40,000,000 | 37.04% | Research funding, strategic partnerships, & institutional adoption. |
| **Liquidity Provision** | 12,000,000 | 11.11% | Initial liquidity for DEXs (Osmosis) & major CEXs. |
| **Developer Core Team** | 10,000,000 | 9.26% | Long-term protocol development incentives (Xyra Labs). |
| **Core Validator Support** | 6,000,000 | 5.55% | Operational grants for the 3 anchor validators. |

**Reward Distribution Logic:**
* **88%** allocated to Stakers & Validators.
* **10%** allocated to the Community Pool (dApp funding & Grants).
* **2%** allocated to the Foundation (operational costs for XYRA-CHAIN, VOID-BREAKER, PAPERLINE).

---

## 7. ADVANCED GOVERNANCE: THE PROPOSAL LIFECYCLE

### 7.1 On-Chain Democracy
Every XYRA token holder is an owner of the network, possessing voting power proportional to their staked amount. The governance system prevents spam through a deposit mechanism:

1. **Submission:** Proposals are submitted with a minimum deposit (e.g., 100 XYRA).
2. **Voting Period:** Lasts for 14 days. Token holders can vote: `Yes`, `No`, `NoWithVeto`, or `Abstain`.
3. **Tallying:** Proposals are valid only if they meet the **Quorum (40%)** and **Yes > 50% Threshold**.
4. **Automatic Execution:** For technical parameter changes, the protocol code executes the update automatically upon approval without manual intervention.

### 7.2 Ultra-Low Gas Economy
Xyra-Chain adopts a highly competitive gas fee structure. This enables innovations previously unfeasible on legacy networks, such as micro-payment streaming, mass-scale on-chain gaming, and high-frequency DeFi.

---

## 8. STRATEGIC ROADMAP

### Phase 1: Genesis Initiation (Q1-Q2 2026) - [COMPLETED]
* Launch of the `xyra-2` genesis block.
* Official integration into the **Cosmos Chain Registry**.
* Official integration into the **Keplr Wallet Registry**.
* Launch of **Xyra Explorer v1** featuring deep-state analysis.
* Stabilization of public gRPC/RPC/API infrastructure.

### Phase 2: Interchain Expansion (Q3-Q4 2026)
* Activation of IBC Relayers to major networks (Cosmos Hub, Osmosis, Celestia).
* Official integration into the **Ping.pub Registry**.
* Official integration into the **Mintscan.io Registry**.
* Developer Grant Program to catalyze dApp ecosystem growth.
* Launch of **Xyra DEX** as the primary liquidity hub for native XYRA assets.

### Phase 3: Smart Contract & EVM Bridge (2027+)
* **CosmWasm** integration for secure, modular smart contract execution.
* Construction of the official **Bridge** to EVM ecosystems (Ethereum & Binance Smart Chain).
* Launch of **Xyra Explorer v2** featuring deep-state analysis.

---

## 9. CONCLUSION
Xyra Chain is not merely a blockchain; it is a commitment to a more transparent and sovereign future. With a strategically distributed supply of 108 Million XYRA and the backing of cutting-edge Cosmos SDK technology, Xyra-2 is poised to become a central pillar in the global blockchain ecosystem. Under the technical leadership of **Rizki Maryanto**, the protocol will continue to innovate toward limitless scalability.

---
**© 2026 Xyra Chain Foundation** *Architected by Rizki Maryanto | Built with Precision and Sovereignty.*
