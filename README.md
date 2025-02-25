# SovereignBit Realms - Smart Contract Documentation

![Stacks L2](https://img.shields.io/badge/Layer-2_Protocol-9146FF?logo=stacks&logoColor=white)
![Bitcoin Compliance](https://img.shields.io/badge/BTC-Compliant-orange?logo=bitcoin)

## Overview

SovereignBit Realms is a Stacks L2-powered MMORPG protocol enabling verifiable ownership of NFT game assets with Bitcoin-settled economics. This contract implements a decentralized gaming primitive combining Clarity's secure smart contracts with Bitcoin's security model.

## Key Features

### Bitcoin-Native NFT Heroes

- ERC-721 compatible digital assets with BRC-20 metadata standards
- 10+ upgradable attributes (power, rarity, skills)
- Bitcoin timestamped ownership provenance

```clarity
(define-non-fungible-token sovereign-heroes uint)
```

### Multi-World Architecture

- Permissioned game worlds with entry requirements
- Cross-world asset portability
- World-specific reward pools

```clarity
(define-map game-worlds {
  world-id: uint
} {
  entry-requirement: uint,
  total-rewards: uint
})
```

### Play-to-Earn Mechanics

- BTC-denominated reward distributions
- STX/BTC dual reward tournaments
- Skill-based proof-of-play mining

### Trustless Trading System

- Atomic NFT/FT swaps
- Time-locked escrow positions
- BRC-20 compliant order matching

```clarity
(define-map active-trades {
  trade-id: uint
} {
  seller: principal,
  btc-price: uint,
  expiry: uint
})
```

## Technical Architecture

### Layer 1 (Bitcoin Mainnet)

- Reward settlement finality
- NFT ownership anchoring via `OP_RETURN`
- Compliance event logging

### Layer 2 (Stacks)

- High-speed battle transactions
- NFT minting/breeding logic
- Real-time leaderboard updates

### Core Components

1. Hero Management System
2. BRC-20 Compliance Engine
3. Cross-Chain Bridge Module
4. Tournament Reward Distributor
5. Anti-Cheat Oracle Network

## Installation

### Prerequisites

- Clarinet SDK v1.5.0+
- Node.js 18.x

## Usage

### Minting a Hero

```clarity
(contract-call? .sovereignbit-realms mint-hero
  "Dragonknight"   ;; Name
  "fire"           ;; Element
  150              ;; Base power
  (list "slash" "fireball")  ;; Skills
)
```

### Joining a World

```clarity
(contract-call? .sovereignbit-realms enter-world
  2  ;; World ID
  500000  ;; STX deposit
)
```

### Initiating Trade

```clarity
(contract-call? .sovereignbit-realms create-trade
  142  ;; Hero ID
  10000000  ;; Price in sats
  1440  ;; Expiry in blocks (~24h)
)
```

## Compliance Features

### BRC-20 Enforcement

- Metadata validation hooks
- SLP-style token restrictions
- Bitcoin block height cooldowns

### KYC/AML Integration

- Tiered trading limits
- OFAC-compliant address checks
- Travel rule metadata fields

## Security

### Key Protection

- Multi-sig administrative controls
- Time-delayed upgrade process
- Emergency freeze capabilities

## Contributing

1. Fork repository
2. Create feature branch (`feat/your-feature`)
3. Submit PR with:
   - Clarinet test coverage
   - Documentation updates
   - Security impact analysis
