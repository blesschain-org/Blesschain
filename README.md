# 🧱 BlessChain

**Next-Generation Home-Node Blockchain Network**  
**Modular · Energy-Aware · Community-Powered**

BlessChain is a Substrate-based blockchain designed to evolve from  
**MVP → TestNet → MainNet**, focusing on home-server validator nodes and distributed edge infrastructure.

---

## 📌 Project Status

**Version:** v0.2.0 (MVP2.0)  
**Stage:** MVP → TestNet Evolution  
**Consensus (Development Mode):** Manual Seal (7-second blocks)  
**Author:** BlessChain Team  
**Project Director:** Joseph Wang  

---

## 🌐 Official Links

- X (Twitter): https://x.com/BlesschainHQ
- Website: https://blesschain.org
- GitHub Organization: https://github.com/blesschain-official

---

# 📘 BlessChain Litepaper v0.1

BlessChain Litepaper v0.1 provides a high-level overview of:

- Vision
- Architectural principles
- Current development status
- Roadmap

This Litepaper does **not** replace technical documentation or source code.

### 📥 Download

https://github.com/blesschain-official/Blesschain/releases/tag/v0.1-litepaper

---

# 🧱 Overview

BlessChain is a lightweight Substrate-based blockchain designed to power the **Bless Ecosystem**, including:

- AI Video & Image services
- TTS / ASR services
- Home-server validator nodes
- Micro data-centers (hotels & homes)
- BBTC token economy
- Distributed compute + storage (HomeCDN)

---

# 🧩 Repository Contents

This repository includes:

- `node/` — BlessChain node implementation
- `runtime/` — Minimal FRAME runtime
- Genesis + chain specification configuration
- Workspace-based build system

---

# ⚙️ Development Configuration

## 🕒 Block Production (Development Mode)

BlessChain development mode uses **manual-seal consensus**  
configured to produce blocks every **7 seconds**.

This configuration is intended for:

- Local testing
- Development
- Controlled TestNet simulation

---

## ▶️ Run Local Development Node (7s Blocks)

```bash
cargo run -p blesschain-node --release -- \
  --dev \
  --validator \
  --consensus manual-seal-7000
```

### Expected Log Output (Example)

```
Prepared block for proposing
Imported #215381 (0x...)
Finalized #215380 (0x...)
```

> Note: Exact log lines may vary depending on configuration.
> Blocks should be produced approximately every 7 seconds.

---

# 🧰 Prerequisites

| Component | Version |
|------------|----------|
| OS | Ubuntu 22.04 / 24.04 LTS |
| Rust | rustc 1.81+ |
| Toolchain | stable |
| Build Target | Native |

---

# 📦 Install Dependencies

```bash
sudo apt update
sudo apt install -y clang cmake make pkg-config libssl-dev git curl build-essential
```

Install Rust:

```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
source $HOME/.cargo/env
rustup default stable
```

---

# 🏗️ Build BlessChain

## Clone Repository

```bash
git clone https://github.com/blesschain-official/Blesschain.git
cd Blesschain
```

## Build

```bash
cargo build --release -p blesschain-node
```

Binary location:

```
target/release/blesschain-node
```

---

# 🧭 Validator Simulation (TestNet Preparation)

Generate keys:

```bash
./target/release/blesschain-node key generate --scheme sr25519
```

Export chain spec:

```bash
./target/release/blesschain-node build-spec > blesschain-testnet.json
```

Run validator:

```bash
./target/release/blesschain-node \
  --chain blesschain-testnet.json \
  --validator
```

---

# 🧱 Project Structure

```
blesschain/
├── node/                 # Node implementation
├── runtime/              # Runtime pallets
├── docs/                 # Whitepaper & architecture
├── Cargo.toml            # Workspace definition
└── README.md
```

---

# 🔍 Troubleshooting

| Issue | Solution |
|--------|----------|
| Benchmarking errors | Disable benchmarking features |
| Permission issues | Ensure correct directory ownership |
| SDK mismatch | Align runtime branch with SDK |

---

# 📜 Version History

| Version | Date | Notes |
|----------|------------|------------|
| v0.1.0-mvp | 2025-10-20 | First runnable MVP |
| v0.1.1-devnet | 2025-10-30 | Minor patches |
| v0.2.0-mvp2.0 | 2025-11-11 | Rebuilt node + runtime |

---

Roadmap:

MVP → TestNet → MainNet

---

# 📜 License

GPL-3.0-only — see LICENSE.

---

# 🕊️ Credits

Developed by the BlessChain Team  
Project Director: Joseph Wang  
🌐 https://blesschain.org
