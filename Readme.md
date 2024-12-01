# Secure Car Access System with NFT & Blockchain

This project involves building a secure car access system using **NFTs**, **crypto wallets**, and **blockchain technology**. The system utilizes a unique token stored in a crypto wallet, which can be used to unlock the car only by interacting with it through a transaction, making the system virtually unbreakable by any unauthorized device.

## Project Overview

The goal is to create a **secure, decentralized, and tamper-proof system** for unlocking vehicles using a unique NFT token. The token is stored in the user's wallet and can only be used to unlock the car if the transaction is authorized through an algorithm present on the user's phone. Additionally, the car itself contains a corresponding token that validates the transaction.

## Key Components

1. **Mobile App**: The mobile app stores the key (NFT) and allows users to authorize transactions that unlock the car.
2. **NFT as a Key**: Each car is assigned a unique NFT, which is stored in the owner's crypto wallet. Only this token can be used to authorize unlocking.
3. **Crypto Wallet**: The app integrates with a crypto wallet (e.g., MetaMask, Trust Wallet) to store the NFT and sign transactions.
4. **Car Crypto Module (CarCryptoModule)**: A cryptographic system embedded in the car that communicates with the app and verifies the cryptographic signatures.
5. **Blockchain**: A blockchain network stores and verifies NFTs, logging transaction details for transparency.
6. **Authorization Algorithm**: The algorithm is responsible for signing and verifying the keys both on the phone and in the car.

## System Workflow

### a) **Key Generation**

1. The user purchases or registers a vehicle, which results in the creation of a unique NFT on the blockchain.
2. The NFT is transferred to the user’s crypto wallet.

### b) **Authorization & Unlocking the Car**

1. The user opens the app on their phone while near the car.
2. The app detects the car via Bluetooth, NFC, or another communication channel.
3. The app:
   - Sends a cryptographic challenge to the car (e.g., in the form of a signed token).
   - Signs the transaction with the private key from the wallet and the NFT, which is then sent to the car module.
4. The car module:
   - Reads and verifies the signed transaction.
   - If the transaction is valid (matches the NFT stored in the car system), the car is unlocked.

### c) **Security**

- The private key of the user never leaves the wallet.
- Any attempt at unauthorized access would require breaking both the user’s private key and gaining physical access to the car.
- All communication between the phone and car is encrypted.

### d) **Adding Other Users**

- The owner can transfer the NFT to another person’s wallet or temporarily grant "access" through sublicensing via a smart contract.

## Technologies & Tools

- **Blockchain**: Ethereum or other NFT-supported networks (e.g., Polygon, Solana).
- **Crypto Wallets**: MetaMask, Trust Wallet, or a custom wallet.
- **Mobile App**: Built using **Flutter** for cross-platform development.
- **Car Communication**:
  - Bluetooth Low Energy (BLE) or NFC for communication.
  - TLS/SSL encryption for secure communication.
- **Backend**:
  - AWS Lambda or Google Cloud Functions for processing requests.
  - Redis for storing temporary session information.

## Advantages of the System

- **Uniqueness**: Each key is a unique NFT on the blockchain.
- **Security**: The user's private key never leaves their wallet.
- **Access Control**: Users can manage permissions for the car using smart contracts.
- **Tamper Resistance**: The use of blockchain makes it extremely difficult to fake the key.

## Emergency Scenario

- If the user loses their phone or access to the wallet, the key can be recovered via the seed phrase or a backup feature in the app.

## Future Enhancements

- Add remote control features (e.g., remote unlocking through the internet).
- Integration with IoT systems in cars (e.g., software updates, GPS tracking).
- Expand to other services like sharing the vehicle via NFTs.

