# Field 2 Table (f2t.io)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)
[![Solana CLI: v2.0.16](https://img.shields.io/badge/Solana%20CLI-v2.0.16-blue)](https://docs.solana.com/cli)
[![Rust: v1.75+](https://img.shields.io/badge/Rust-v1.75%2B-orange)](https://www.rust-lang.org/)

A decentralized marketplace revolutionizing local food commerce through blockchain-based farm shares, NFT-driven access control, and automated regulatory compliance.

## 🌟 Features

### Core Technologies
- 🔗 **Solana Smart Contracts** - Rust-based programs for farm share and compliance management
- 🎫 **Dynamic NFTs** - Metaplex-powered role and attribute management
- 🗃️ **NFT.storage** - Decentralized content storage with IPFS
- 🌐 **Yew Framework** - Rust-based WebAssembly frontend
- ⚡ **Serverless Rust** - AWS Lambda functions with custom runtime

### Key Components
- **Decentralized Storage** - IPFS-based permanent data availability
- **Farm Share Framework** - Legal structure enabling interstate commerce
- **Compliance Automation** - Real-time verification with NFT attributes
- **Zero-Trust Security** - Blockchain-verified access control

## 🚀 Getting Started

### Prerequisites
```bash
# Required versions
rustc 1.75.0 or higher
cargo 1.75.0 or higher
solana-cli 2.0.16
```

### Environment Setup
```bash
# Install Rust
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh

# Install Solana CLI
sh -c "$(curl -sSfL https://release.solana.com/v2.0.16/install)"

# Install WebAssembly tools
cargo install wasm-pack
cargo install trunk
rustup target add wasm32-unknown-unknown
```

### Development Setup
```bash
# Clone repository
git clone https://github.com/yourusername/f2t.io.git
cd f2t.io

# Install workspace dependencies
cargo build

# Configure environment
cp .env.example .env
# Edit .env with your configurations

# Start development server
trunk serve
```

## 🏗️ Project Structure

```
f2t.io/
├── programs/               # Solana smart contracts
│   ├── farm_share/        # Farm share program
│   └── access_control/    # NFT access control
├── app/                   # Yew WebAssembly frontend
│   ├── src/              # Frontend source code
│   └── Cargo.toml        # Frontend dependencies
├── lambda/               # Serverless functions
│   ├── src/             # Lambda handlers
│   └── Cargo.toml       # Lambda dependencies
└── lib/                 # Shared Rust libraries
```

## 🔧 Development

### Smart Contract Development
```bash
# Build Solana programs
cargo build-bpf

# Run tests
cargo test-bpf

# Deploy program
solana program deploy target/deploy/farm_share.so
```

### Frontend Development
```bash
# Start Yew development server
trunk serve

# Build for production
trunk build --release
```

### Lambda Development
```bash
# Build Lambda functions
cargo lambda build

# Test locally
cargo lambda watch

# Deploy
cargo lambda deploy
```

### Local Development Dependencies
```toml
[workspace]
members = [
    "app",
    "programs/*",
    "lambda",
    "lib"
]

[workspace.dependencies]
yew = "0.21"
wasm-bindgen = "0.2"
solana-program = "1.17"
anchor-lang = "0.28"
```

## 📖 Documentation

- [System Architecture](./docs/architecture.md)
- [Access Control](./docs/accessControlSystem.md)
- [Smart Contracts](./docs/smartContracts.md)
- [AWS Integration](./docs/awsIntegration.md)
- [API Reference](./docs/apiReference.md)

## 📊 Technical Architecture

```mermaid
graph TB
    subgraph "Frontend"
        A[Yew WebAssembly]
        B[Solana Wallet]
    end
    
    subgraph "Storage"
        C[NFT.storage]
        D[IPFS]
    end
    
    subgraph "Blockchain"
        E[Solana Programs]
        F[NFT Metadata]
    end
    
    subgraph "Serverless"
        G[Rust Lambda]
        H[DynamoDB Index]
    end
    
    A --> C
    A --> E
    C --> D
    E --> F
    G --> H
    G --> D
```

## 🤝 Contributing

See our [Contributing Guide](CONTRIBUTING.md) for:
- Development workflow
- Code standards
- Testing requirements
- Documentation guidelines

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 📞 Contact

- [Twitter](https://twitter.com/f2t_io)
- Email: support@f2t.io

---
Built with 🦀 Rust and ❤️ for local food communities