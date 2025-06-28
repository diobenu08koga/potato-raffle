# Super Potato Raffle Program

A raffle program where users can buy tickets using SOL to win NFTs.

## Install Dependencies
- Install `node` and `yarn`
- Install `ts-node` globally
- Prepare your Solana wallet (see `/home/---/.config/solana/id.json` in test case)

## Usage
- Main script: `/cli/script.ts`
- Program account types: `/cli/types.ts`
- IDL for JS binding: `/cli/raffle.json`

To test script functions:
- Adjust commands in `script.ts` as needed
- Set the `ANCHOR_WALLET` environment variable for `ts-node` in `package.json`
- Run `yarn ts-node`

## Features

### For Smart Contract Owners
- Initialize the contract for global account allocation: `initProject`
- Add collections to the raffle site: `addCollection`

### For Raffle Creators
- Create raffles with `createRaffle` function
- Withdraw NFTs if no tickets are sold within the time limit: `withdrawNft`

### For Raffle Participants
- Buy tickets using `buyTicket`
- Reveal winners with `revealWinner`

### For Raffle Winners
- Claim rewards using `claimReward`

## Deployment

1. Clone the repository
2. In the `raffle` folder, run `yarn`
3. Run `anchor build`
4. Get the program ID and update it in:
   - `lib.rs` line 20: `declare_id!("PROGRAM_ID");`
   - `Anchor.toml` line 4: `raffle = "PROGRAM_ID"`
   - `scripts.ts` line 21: `const PROGRAM_ID = "PROGRAM_ID";`
5. Run `anchor build` again
6. Deploy with `solana program deploy /path/to/raffle.so`
7. Uncomment line 54 in `script.ts` and run `yarn ts-node`

## Requirements

### User Features
- Collection registration
- Raffle creation (costs ~0.4 SOL per NFT)
- Ticket purchasing
- NFT withdrawal (after end time with no tickets sold)
- Winner revelation
- Reward claiming

### Admin Features
- Collection approval/denial system

# 🥔🥔🥔 Super Potato NFT Raffle | Solana | Next.js + Typescript

<p align="center">
    <img src="./.github/preview.png" alt="Super potato" />
</p>

## 📖 Requirements
### 👶 User side
- Collection register
- Raffle create <br />
  They will have to pay about 0.4 SOL per NFT when creating a raffle.
- Buy tickets
- Withdraw NFT (after end time & and not sold any tickets)
- Reveal winner
- Claim reward
### 👨‍💻 Admin side
- User-registered Accept/Deny of collection
### Like FFF Raffle (famous fox federation)
[rafffle.famousfoxes.com](https://rafffle.famousfoxes.com/)
<br />

## Mindfolk Landing Page
[www.mindfolk.art](https://www.mindfolk.art/)

## 🌐 Deployed
[superpotato-raffle.herokuapp.com/](https://superpotato-raffle.herokuapp.com/)


## 🛠 ※ SET PROJECT ENVIRONMENT
### Firebase set
Replace firebase configuration values <br />
`src/api/firebase.ts` <br/>
```tsx
const firebaseConfig = {
    apiKey: "AIzaSyAI_r1Rs11kIsWJFiCVA4aGt58ffsZrclY",
    authDomain: "mindfolk-raffle-afb92.firebaseapp.com",
    projectId: "mindfolk-raffle-afb92",
    storageBucket: "mindfolk-raffle-afb92.appspot.com",
    messagingSenderId: "106626330620",
    appId: "1:106626330620:web:c3343f7736902e58774c79",
    measurementId: "G-NHD9LYKTVJ"
};
```
### Project config data
`src/config.tsx` <br />
```tsx
export const NETWORK = "mainnet-beta"; //mainnet-beta | devnet
export const ADMINS = [
    "7TBRMXkRbVpRWgLkrrTaqFJvXSMkMwnNKEZ4dbRh8Lnf",
    "FePFmE1CbbTkiKg4K9A41dQcXfhPqLSJrEBcdXwBj3aa",
    "A8rgsJecHutEamvb7e8p1a14LQH3vGRPr796CDaESMeu" // developer wallet address
]

// deployed url
export const LIVE_URL = "https://superpotato-raffle.herokuapp.com/" 
// treasury wallet address
export const TREASURY_WALLET = new PublicKey('BEQZXkjg1BzY5349FXGPgvsbySWw5R7zjEC4xQhzmQR5');
//smart contract program id
export const PROGRAM_ID = "Geb2fkVJMgNbjPwMkcjfR3n4AiN7DKqKwctFwfErkbn7"; 
// solana RPC url
export const RPC_URL = "https://a2-mind-prd-api.azurewebsites.net/rpc";

```

## Install

```bash
npm run install
# or
yarn install
```
## Development

```bash
npm run dev
# or
yarn dev
```

## 🔥 Database
Google **Firebase**
- **collections** <br />
    When users send a request to register a Collection, it is stored in the database Collection calls **collections**.<br />
    Admin can **Accept** or **Deny** those collections. <br />
    All collections are also stored on the blockchain.
- **raffles** <br />
    When user create a raffle, it saved also database `raffles` document. <br />
    Raffle on db is updated, when those actions <br />
    `buy tickets`, `reveal winner`, `withdraw nft`, `claim reward`
  
