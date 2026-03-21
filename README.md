Xyra Chain (xyra-2) 🚀

<p align="center">
  <img src="https://github.com/rizkimaryanto7-creator/chain-registry/blob/master/xyra/images/xrc.png" width="160"/>
</p><p align="center">
Next-generation blockchain powered by Proof-of-Stake consensus. 
This blockchain is focused on intensive communities
</p><p align="center">
<a href="https://github.com/rizkimaryanto7-creator/xyra-chain/actions">
<img src="https://img.shields.io/github/actions/workflow/status/rizkimaryanto7-creator/xyra-chain/ci.yml?branch=main">
</a>
<a href="https://github.com/rizkimaryanto7-creator/xyra-chain/releases">
<img src="https://img.shields.io/github/v/release/rizkimaryanto7-creator/xyra-chain">
</a>
<a href="#">
<img src="https://img.shields.io/badge/network-mainnet-blue">
</a>
</p>---

🌌 Overview

Xyra Chain is a decentralized blockchain designed for scalable digital assets and decentralized applications (dApps).

Built using the Cosmos SDK, Xyra leverages Proof-of-Stake (PoS) consensus to provide high performance, energy efficiency, and strong network security.

The network is powered by the native token XYRIUM, which is used for:

- transaction fees
- staking and validator security
- governance
- decentralized applications

---

🌐 Network Information

Parameter| Value
Network| Xyra Mainnet
Chain ID| "xyra-2"
Consensus| Proof-of-Stake
Block Time| ~5 seconds
Genesis Date| 2026-03-11
Max Validators| 100

---

💰 Token Information

Property| Value
Token Name| Xyrium
Symbol| XYRIUM
Base Denomination| "uXyrium"
Conversion| 1 XYRIUM = 1,000,000 uXyrium
Total Supply| 108,000,000 XYRIUM

---

📊 Economic Parameters

Parameter| Value
Inflation Range| 7% – 20%
Target Inflation| 13%
Community Tax| 2%
Unbonding Time| 21 days
Blocks Per Year| 6,311,520

---

🌍 Public Network Endpoints

Service| Endpoint
RPC| https://rpc.xyra-mainnet.org
REST API| https://api.xyra-mainnet.org
gRPC| grpc.xyra-mainnet:9090
Explorer| https://www.xyra-mainnet.org

---

🌱 Seed Nodes

Seed nodes help new nodes discover peers in the network.

9b9f09a507ce82beedd8fc200bc19a9534d3aadf@31.97.75.83:26656
b1577b70e4b30ba2f850e35cbccc0c0199edf77e@72.62.121.184:26656

Add them to:

~/.xyra/config/config.toml

---

🔗 Persistent Peers

9b9f09a507ce82beedd8fc200bc19a9534d3aadf@31.97.75.83:26656
b1577b70e4b30ba2f850e35cbccc0c0199edf77e@72.62.121.184:26656

---

🛠 Quick Start

1️⃣ Download Binary

Download the latest binary from:

https://github.com/rizkimaryanto7-creator/xyra-chain/releases

Install:

chmod +x xyrad
sudo mv xyrad /usr/local/bin/

Verify:

xyrad version --long

---

⚙ Node Initialization

Initialize a node:

xyrad init <YOUR_MONIKER> --chain-id xyra-2

---

📦 Genesis Setup

Download the official "genesis.json".

Place it in the configuration folder:

cp genesis.json ~/.xyra/config/genesis.json

---

🚀 Start Node

xyrad start

Your node will begin syncing with the Xyra network.

---

🛡 Become a Validator

Create wallet:

xyrad keys add validator

Check address:

xyrad keys show validator -a

Create validator:

xyrad tx staking create-validator \
--amount=1000000uXyrium \
--pubkey=$(xyrad tendermint show-validator) \
--moniker="<YOUR_MONIKER>" \
--chain-id=xyra-2 \
--commission-rate="0.10" \
--commission-max-rate="0.20" \
--commission-max-change-rate="0.01" \
--min-self-delegation="1" \
--from=validator

---

🔐 Network Security

Parameter| Value
Max Validators| 100
Slash (Double Sign)| 5%
Slash (Downtime)| 1%
Downtime Jail Duration| 5 minutes

---

👨‍💻 Development

Clone repository:

git clone https://github.com/rizkimaryanto7-creator/xyra-chain.git
cd xyra-chain

Install dependencies:

go mod tidy

Build binary:

make install

Check version:

xyrad version --long

---

📂 Project Structure

xyra-chain
│
├── app/                # Blockchain application logic
├── cmd/xyrad           # Main binary entry point
├── proto/              # Protobuf definitions
├── x/                  # Cosmos modules
│
├── scripts/            # Utility scripts
├── docs/               # Documentation
│
└── .github/
    └── workflows/      # CI/CD pipelines

---

🤝 Contributing

Contributions are welcome.

Steps:

1. Fork repository
2. Create new branch
3. Commit changes
4. Submit pull request

---

📜 License

This project is open-source and released under the License from cosmos sdk.

---

👤 Author

Created and maintained by Rizkimaryanto7-creator 

---

© 2026 Rizki Maryanto
