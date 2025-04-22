# GiveFi User Flow

Hey, I’m Sukuna, and this is how **GiveFi** will work for users. I want judges and the NERO community to see exactly what it feels like to use this micro-charity dApp. It’s designed to be dead simple, gas-free, and fun, so anyone can jump in and start making a difference. Below, I’ll walk you through the user journey, with an example to make it real.

## The Big Picture

GiveFi’s a SocialFi-GameFi dApp on NERO Chain where you donate small amounts (like 10¢) to verified charity campaigns, earn **Impact Point NFTs**, compete on leaderboards, and join quests. A DeFi staking option keeps the giving going. NERO’s Paymaster makes every step gas-free, so it feels like a Web2 app—no crypto headaches.

## Step-by-Step User Flow

Here’s what a user does, from signing up to changing the world:

1. **Sign Up (1 Minute, Gas-Free)**  
   - You open the GiveFi app (web or mobile) and sign up with your email, Google, or X account.  
   - Behind the scenes, Web3Auth and NERO’s Paymaster create a smart contract wallet (ERC-4337) without you needing a seed phrase or MetaMask.  
   - **Paymaster Role**: Covers gas for wallet creation (Type 0, sponsored).  
   - **Example**: Sarah, a college student, signs up with her Gmail. She’s ready to go in 30 seconds, no crypto knowledge needed.

2. **Pick a Cause & Donate (1 Minute, Gas-Free)**  
   - Browse campaigns, like “Books for Kids” ($100 goal, $50 raised) or “Clean Water for a Village” ($200 goal). Each has a photo and story.  
   - Tap to donate 10¢, 50¢, or a custom amount (paid via card or stablecoin like USDC).  
   - **Paymaster Role**: Sponsors gas for the donation transaction (Type 0), so Sarah pays only her 50¢ donation.  
   - **Example**: Sarah picks “Books for Kids” and donates 50¢ to help buy pencils. The app says, “You’re awesome, Sarah!”

3. **Earn an Impact Point NFT (Instant, Gas-Free)**  
   - After donating, you get a unique Impact Point NFT, minted on NERO Chain. It’s like a badge showing your impact (e.g., “Sarah’s 50¢ Book Donation”).  
   - The NFT appears in your app wallet, viewable anytime.  
   - **Paymaster Role**: Covers gas for NFT minting (Type 0).  
   - **Example**: Sarah’s NFT pops up with a cute pencil graphic. She taps to see its details on NERO’s blockchain.

4. **Compete on Leaderboards (Ongoing)**  
   - Your donation adds points to your profile, shown on a leaderboard (e.g., “Sarah: 50 Points, #12”).  
   - Leaderboards reset weekly, encouraging more donations.  
   - **Paymaster Role**: Gas for updating leaderboard scores is sponsored (Type 0).  
   - **Example**: Sarah sees she’s close to the Top 10 and wants to donate again to climb higher.

5. **Join Quests (Optional, Gas-Free)**  
   - Take on fun challenges, like “Fund 10 Books This Week” for a bonus NFT or “Daily Donation Streak” for extra points.  
   - Quests encourage community engagement and repeat donations.  
   - **Paymaster Role**: Gas for quest actions (e.g., joining, claiming rewards) shifts to token-based (Type 2, paid in GiveFi tokens) after onboarding.  
   - **Example**: Sarah joins “Fund 10 Books” and donates another 50¢, earning a bonus “Book Hero” NFT.

6. **Stake or Share (Optional)**  
   - Stake your donations in a DeFi pool to earn yield, funding future campaigns.  
   - Share your donation on X (e.g., “I helped kids get books for 50¢! #GiveFi”) for bonus leaderboard points.  
   - **Paymaster Role**: Staking uses token-based gas (Type 2); sharing is off-chain, no gas.  
   - **Example**: Sarah stakes her 50¢ to support more causes and tweets her NFT, earning 10 extra points.

## Example Journey: Sarah’s First Day

- **9:00 AM**: Sarah signs up with Gmail, no wallet needed.
- **9:02 AM**: She donates 50¢ to “Books for Kids,” gas-free.
- **9:03 AM**: Gets her first Impact Point NFT and sees her name on the leaderboard (#12).
- **9:05 AM**: Joins the “Fund 10 Books” quest and donates another 50¢, earning a bonus NFT.
- **9:10 AM**: Shares “I’m helping kids with #GiveFi!” on X, boosting her score.
- **9:15 AM**: Stakes her $1 total donation in the pool, excited to keep the impact going.

Total time: 15 minutes. Total cost: $1 (her donations). Sarah’s hooked, and she didn’t touch a single gas fee.

## Why This Flow Rocks

- **Simple**: Feels like a Web2 app, no crypto jargon.
- **Inclusive**: Sarah’s a student, but anyone can join—no wearables or crypto skills needed.
- **Fun**: NFTs, leaderboards, and quests make giving addictive.
- **Impactful**: Every 10¢ helps real causes, tracked transparently on NERO Chain.

## Tech Behind the Flow

- **Sign-Up**: Web3Auth + NERO’s UserOp SDK for wallet creation.
- **Donations/NFTs**: Solidity contracts on NERO Chain, minted gas-free via Paymaster.
- **Leaderboards/Quests**: On-chain updates (Paymaster-sponsored) with off-chain UI.
- **Staking**: DeFi pool contract, with token-based gas for repeat users.
- **Storage**: IPFS for campaign stories and NFT images.

This flow’s ready to scale in Wave 2 with an MVP. Check out [README.md](README.md) for the big picture, and let me know your thoughts on NERO’s Discord or X!

