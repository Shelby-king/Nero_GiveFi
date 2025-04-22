# GiveFi Architecture Overview

This is how **GiveFi** will come to life on NERO Chain! I’m not drowning you in tech jargon—this is a high-level look at how the pieces fit together to make micro-charity feel like a Web2 app. GiveFi’s all about gasless donations, Impact Point NFTs, and community fun, and NERO’s Paymaster is the glue that makes it seamless. Here’s the big picture for Wave 1, with plans to build it out in Wave 2.

## System Overview

GiveFi’s a SocialFi-GameFi dApp with a DeFi twist, letting users donate small amounts (e.g., 10¢) to causes, earn NFTs, and stake funds for sustainability. It’s built on NERO Chain, using Paymaster for a gasless, Web2-like experience. The system has four main parts: the frontend (app), backend (logic), blockchain (NERO), and storage (IPFS).

## Components

1. **Frontend (User Interface)**  
   - **What It Does**: The app users see—think a clean, colorful interface for signing up, donating, checking leaderboards, and joining quests.  
   - **Tech**: React or NextJS, with Web3Auth for email/social login (no wallet hassle).  
   - **Paymaster Role**: Uses NERO’s UserOp SDK to send gasless transactions (e.g., donations, NFT claims) to the blockchain.  
   - **Example**: Sarah opens the app, signs in with Gmail, and donates 50¢ without touching a wallet.

2. **Backend (Logic Layer)**  
   - **What It Does**: Handles off-chain logic, like processing donations, updating leaderboards, and managing quests.  
   - **Tech**: Node.js or similar, connecting the frontend to NERO Chain via APIs.  
   - **Paymaster Role**: Bundles user actions (e.g., donate + claim NFT) into UserOperations, sent to NERO’s bundler for gasless execution.  
   - **Example**: When Sarah donates, the backend triggers a gasless transaction to mint her NFT.

3. **Blockchain (NERO Chain)**  
   - **What It Does**: Powers donations, NFT minting, leaderboards, and staking with smart contracts.  
   - **Tech**: Solidity contracts on NERO Chain (EVM-compatible):  
     - `Donation.sol`: Tracks donations and campaign progress.  
     - `ImpactNFT.sol`: Mints unique Impact Point NFTs.  
     - `Leaderboard.sol`: Updates user scores.  
     - `Staking.sol`: Manages DeFi pool for donation yield.  
   - **Paymaster Role**: Paymaster sponsors gas for onboarding (Type 0, e.g., first donation) and uses token-based gas (Type 2, GiveFi tokens) for repeat actions like quests.  
   - **Example**: Sarah’s 50¢ donation is recorded on-chain, and her NFT is minted, all gas-free.

4. **Storage (IPFS)**  
   - **What It Does**: Stores campaign details (e.g., photos of kids with books) and NFT metadata (e.g., Sarah’s pencil badge).  
   - **Tech**: IPFS for decentralized, scalable storage.  
   - **Paymaster Role**: No gas needed for off-chain storage, but NFT metadata links are stored on-chain gas-free.  
   - **Example**: Sarah sees a campaign photo on IPFS, making the cause feel real.

## Paymaster & AA Integration

NERO’s Paymaster is the heart of GiveFi’s seamless UX. Here’s how it works:
- **Gasless Onboarding**: New users (like Sarah) sign up and donate without paying gas. Paymaster sponsors these transactions (Type 0) using NERO’s no-code dashboard.  
- **Hybrid Model**: After onboarding, quests and repeat donations use GiveFi tokens for gas (Type 2), keeping costs invisible.  
- **UserOp SDK**: Batches actions (e.g., donate + mint NFT) into one UserOperation, sent to NERO’s bundler for efficiency.  
- **AA Wallets**: Web3Auth creates ERC-4337 smart wallets on signup, so users never deal with seed phrases.

This setup nails the 30% AA Integration criteria by making Web3 feel like Web2.

## Architecture Diagram (Text-Based)

[User] --> [Frontend: React, Web3Auth]
               |
               v
[Backend: Node.js] --> [NERO Chain: Solidity Contracts]
               |          - Donation.sol
               |          - ImpactNFT.sol
               |          - Leaderboard.sol
               |          - Staking.sol
               v
[Paymaster: Gasless via UserOp SDK] --> [Bundler]
               |
               v
[IPFS: Campaign & NFT Metadata]


(In Wave 2, I’ll add a visual diagram in Canva!)

## Why This Works

- **Simple**: Users don’t see the blockchain—it’s all hidden behind a friendly app.  
- **Scalable**: NERO’s high throughput handles thousands of donations.  
- **Inclusive**: No wallets or crypto skills needed, just a phone.  
- **Impactful**: Every component supports real-world charity with transparent tracking.

This is a high-level plan for Wave 1, but I’m ready to start coding contracts and wiring up the frontend in Wave 2. Check out [README.md](README.md) for the big vision and [USER_FLOW.md](USER_FLOW.md) for how users experience it. Let me know your thoughts on NERO’s Discord or X!

