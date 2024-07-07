# Polygon-Bridge
---
## NFT Collection Project

## Overview

This project involves creating a 5-item NFT collection using DALLE 2 or Midjourney, storing the items on IPFS using pinata.cloud, and deploying an ERC721 or ERC1155 contract to the sepolia Ethereum Testnet. The project includes additional functionalities like mapping the NFT collection using the Polygon network token mapper and batch minting and transferring NFTs using Hardhat scripts.

## Tools Used

- **Hardhat**: A development environment to compile, deploy, test, and debug Ethereum software.
- **Foundry (optional)**: A blazing fast, portable, and modular toolkit for Ethereum application development written in Rust.

## Project Rubric

To successfully complete the Final Challenge, your project should meet the following criteria:

### 1. Generate a 5-item Collection
- Use DALLE 2 or Midjourney to generate a 5-item NFT collection.
- Store these items on IPFS using pinata.cloud.

### 2. Deploy an ERC721 or ERC1155 Contract
- Deploy your NFT contract to the sepolia Ethereum Testnet.
- Implement a `promptDescription` function in the contract that returns the prompt used to generate the images.

### 3. Map Your NFT Collection
- Use the Polygon network token mapper to map your NFT collection. Note: this step is optional but helpful for visualization.

### 4. Batch Mint NFTs
- Write a Hardhat script to batch mint all NFTs. Using the ERC721A standard is optimal for this step.

### 5. Batch Transfer NFTs
- Write a Hardhat script to batch transfer all NFTs from Ethereum to Polygon amoy using the FxPortal Bridge.
  - Approve the NFTs to be transferred.
  - Deposit the NFTs to the Bridge.

## Setup Instructions

1. **Clone the Repository**
   ```bash
   git clone <repository-url>
   cd <repository-name>
   ```

2. **Install Dependencies**
   ```bash
   npm install
   ```

3. **Configure Environment Variables**
   Create a `.env` file in the root directory and add the necessary environment variables:
   ```env
   INFURA_PROJECT_ID=<your-infura-project-id>
   sepolia_PRIVATE_KEY=<your-sepolia-private-key>
   PINATA_API_KEY=<your-pinata-api-key>
   PINATA_API_SECRET=<your-pinata-api-secret>
   ```

4. **Compile Contracts**
   ```bash
   npx hardhat compile
   ```

5. **Deploy Contracts**
   ```bash
   npx hardhat run scripts/deploy.js --network sepolia
   ```

6. **Mint NFTs**
   ```bash
   npx hardhat run scripts/mint.js --network sepolia
   ```

7. **Transfer NFTs to Polygon amoy**
   ```bash
   npx hardhat run scripts/approveAndTransfer.js --network sepolia
   ```

## Scripts

### Deploy Script (`scripts/deploy.js`)
This script deploys the ERC721 or ERC1155 contract to the sepolia Ethereum Testnet.

### Mint Script (`scripts/mint.js`)
This script batch mints all NFTs using the ERC721A standard.

### Approve and Transfer Script (`scripts/approveAndTransfer.js`)
This script approves and transfers all NFTs from Ethereum to Polygon amoy using the FxPortal Bridge.

## Contract Details

- **Contract Name**: Your contract name here
- **Network**: sepolia Ethereum Testnet
- **Standard**: ERC721 or ERC1155

## promptDescription Function

The `promptDescription` function should return the prompt used to generate the images for the NFTs. Here’s an example implementation:

```solidity
function promptDescription(uint256 tokenId) public view returns (string memory) {
    return prompts[tokenId];
}
```

## Notes

- Ensure you have sufficient testnet ETH in your sepolia wallet for deployment and transactions.
- Use the Polygon token mapper to visualize your NFT collection on the Polygon network.
- Refer to the Hardhat and Foundry documentation for additional support and troubleshooting.

## Conclusion

This project demonstrates the creation, deployment, and cross-chain transfer of an NFT collection using Hardhat, Foundry, and various blockchain networks and tools. By following the setup instructions and scripts provided, you can successfully complete the Final Challenge and showcase your skills in NFT development and blockchain integration.
