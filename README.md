# Super Potato Raffle Program

A Solana-based raffle program where users can buy tickets using SOL to win NFTs.

## Overview

This project implements a decentralized raffle system similar to Famous Fox Federation's raffle platform. Users can create raffles, buy tickets, and win NFT prizes through a transparent blockchain-based system.

## Features

### For Smart Contract Owners
- Initialize contract for global account allocation
- Add collections to the raffle platform
- Collection approval/denial system

### For Raffle Creators
- Create raffles with configurable parameters
- Withdraw NFTs if no tickets are sold within time limit
- Set ticket prices and duration

### For Raffle Participants
- Buy tickets using SOL
- View raffle details and odds
- Participate in multiple raffles

### For Raffle Winners
- Claim rewards automatically
- Transparent winner selection

## Installation

```bash
npm install
# or
yarn install
```

## Development

```bash
npm run dev
# or
yarn dev
```

## Deployment

1. Clone the repository
2. Install dependencies: `yarn install`
3. Build the program: `anchor build`
4. Update program ID in configuration files
5. Deploy: `solana program deploy /path/to/raffle.so`
6. Initialize the project

## Configuration

### Environment Setup
- Set Solana network (mainnet-beta/devnet)
- Configure admin wallet addresses
- Set treasury wallet address
- Configure RPC endpoint

### Firebase Configuration
- Collections database for NFT collections
- Raffles database for raffle management
- Real-time updates for raffle status

## Project Structure

- `backend/` - Solana smart contracts
- `frontend/` - Next.js web application
- `cli/` - Command line interface
- `migrations/` - Deployment scripts

## Requirements

- Node.js and Yarn
- Solana Command Line Toolkit
- Anchor framework
- Firebase project setup

## License

MIT License
