# Xyra Chain (xyra-2) 🚀

Xyra Chain is a high-performance, independent blockchain protocol built with the Cosmos SDK.

## 🔗 Network Specifications
* **Chain ID**: `xyra-2`
* **Native Token**: `uXyrium` (XYRIUM)
* **Initial Supply**: 108,000,000 XYRIUM

## 🛠 Installation
1. Download `xyrad` from the Releases tab.
2. `chmod +x xyrad && sudo mv xyrad /usr/local/bin/`
3. `xyrad init <MONIKER> --chain-id xyra-2`


README.md
Markdown
# Xyra Chain (xyra-2) 🚀

Xyra Chain is a next-generation blockchain built using the Cosmos SDK, featuring a robust Proof-of-Stake (PoS) consensus and a tailored economic model for decentralized applications.

## 🔗 Network Specifications
* **Chain ID**: `xyra-2`
* **Moniker**: `XYRA-CHAIN`
* **Genesis Time**: 2026-03-11
* **Native Denom**: `uXyrium` (XYRIUM)
* **Base Unit**: `1 XYRIUM = 1,000,000 uXyrium`

## 📊 Tokenomics & Parameters
* **Total Supply**: 108,000,000 XYRIUM (`108,000,000,000,000 uXyrium`)
* **Inflation**: 7% - 20% (Target: 13%)
* **Staking Unbonding Time**: 21 days (`1814400s`)
* **Blocks Per Year**: 6,311,520 (Targeting ~5s block time)
* **Community Tax**: 2%

---

## 🛠 Quick Start

### 1. Download Binary
Ambil binary `xyrad` dari tab [Releases](https://github.com/rizkimaryanto7-creator/xyra-chain/releases).

```bash
# Setup permissions
chmod +x xyrad
sudo mv xyrad /usr/local/bin/
2. Initialize Node
Bash
xyrad init <YOUR_MONIKER> --chain-id xyra-2
3. Genesis Setup
Download file genesis.json (tersedia di network-v2 archive) dan pindahkan ke folder config:

Bash
cp genesis.json ~/.xyra/config/genesis.json
🛡 Network Security
Xyra Chain dikawal oleh validator dengan parameter keamanan ketat:

Max Validators: 100

Slash Fraction (Double Sign): 5%

Slash Fraction (Downtime): 1%

Downtime Jail Duration: 10 minutes

👨‍💻 Development
Build from Source
Bash
git clone [https://github.com/rizkimaryanto7-creator/xyra-chain.git](https://github.com/rizkimaryanto7-creator/xyra-chain.git)
cd xyra-chain
go mod tidy
make install
Copyright © 2026 Rizki Maryanto.


---

### Apa yang Baru di README ini?
1. **Akurasi Chain ID**: Saya ganti dari `Xyra-1` ke `xyra-2` sesuai file JSON terbaru kamu.
2. **Detail Unit**: Saya tambahkan konversi `uXyrium` ke `XYRIUM` (exponent 6) supaya user tidak bingung dengan jumlah nol yang banyak.
3. **Parameter Teknis**: Saya masukkan angka *Unbonding Time* (21 hari) dan *Inflation* yang ada di `app_state`.
4. **Alamat Akun**: Saya sudah mencatat ada 7 akun dasar yang sudah terdaftar di genesis kamu.

**Langkah selanjutnya:**
Tinggal masukkan kode di atas ke file `README.md` di Ubuntu, lalu push:
```bash
git add README.md
git commit -m "docs: sync readme with xyra-2 genesis parameters"
git push origin main
Sudah siap untuk mengajak orang lain bergabung jadi validator di xyra-2, Bro? Saya bisa bantu buatkan instruksi cara gentx kalau kamu butuh!


---
Copyright © 2026 Rizki Maryanto. 


