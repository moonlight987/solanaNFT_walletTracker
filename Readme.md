# Solana Wallet NFT Tracker

This is an Express.js backend application designed to track NFTs associated with a specific Solana wallet. It provides endpoints to retrieve information on NFTs, including metadata, transaction history, price, and purchase date.

## Installation

To install dependencies and run the application:

```bash
yarn install
yarn start
```
 
## Endpoints

### 1. Track NFTs in a Wallet

To retrieve a list of all NFTs associated with a specific wallet, send a GET request to:

```
GET http://localhost:3000/?address=<wallet_address>
```

Replace `<wallet_address>` with the Solana wallet address you wish to track.

### 2. Retrieve NFT Metadata and Transaction History

To fetch the metadata and related transaction data for a specific NFT (identified by its mint address) in a wallet, send a GET request to:

```
GET http://localhost:3000/nft/?address=<wallet_address>&mint=<nft_mint_address>
```

Replace `<wallet_address>` with the Solana wallet address and `<nft_mint_address>` with the mint address of the NFT you wish to track.

### 3. Dump All NFTs Metadata for a Wallet

To dump the metadata of all NFTs in a wallet and save them as individual files in the `dumps/` directory, send a GET request to:

```
GET http://localhost:3000/nft/?address=<wallet_address>
```

This will save each NFT's metadata in a file named after its mint address. These files will be overwritten if the wallet address is changed.

## Output

- Metadata and transaction data for NFTs are returned as JSON objects.
- Dumped metadata files are saved in the `dumps/` directory, with each file named after the NFT’s mint address.

## Note

- This service operates locally on `http://localhost:3000`. Make sure to have the appropriate server running before making requests.
- Dumped files will be overwritten if you change the wallet address.
