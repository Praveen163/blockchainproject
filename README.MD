# DocVer: Blockchain Document Verification Platform

DocVer is a web-based platform that leverages blockchain technology to provide secure, efficient, and tamper-proof document verification for institutions and organizations. The platform allows users to upload, verify, and manage documents, ensuring authenticity and trust in digital operations.

## Features

- **Blockchain-Backed Verification:** Uses Ethereum smart contracts to store and verify document hashes, ensuring immutability and transparency.
- **IPFS Integration:** Documents are uploaded to IPFS (via Infura), providing decentralized and persistent storage.
- **MetaMask Authentication:** Users interact with the platform using MetaMask for secure wallet-based authentication and transaction signing.
- **Document Upload:** Upload PDF or image files, which are hashed and stored on the blockchain and IPFS.
- **Document Verification:** Instantly verify the authenticity of any document by uploading it; the platform checks the hash against the blockchain.
- **Document Deletion:** Authorized users can remove document hashes from the blockchain.
- **Admin Dashboard:** Manage exporters (institutions), add/edit/delete their information, and monitor platform statistics.
- **QR Code Generation:** Downloadable QR codes for each uploaded document, linking to its verification.
- **Responsive UI:** Built with Bootstrap 5 and enhanced with animations (AOS) for a modern user experience.

## Smart Contract

The core of DocVer is the `Verification.sol` smart contract, which manages:
- Exporter (institution) registration and management (add, edit, delete).
- Document hash storage and lookup.
- Ownership and authorization logic for secure operations.

## Tech Stack

- **Frontend:** HTML, CSS (Bootstrap, AOS), JavaScript
- **Blockchain:** Ethereum (Solidity smart contract)
- **Web3 Integration:** [web3.js](https://web3js.readthedocs.io/)
- **File Storage:** [IPFS](https://ipfs.io/) via [Infura](https://infura.io/)
- **Wallet:** [MetaMask](https://metamask.io/)
- **QR Code:** [qrcode.js](https://github.com/davidshimjs/qrcodejs)
- **UI Libraries:** [Bootstrap 5](https://getbootstrap.com/), [AOS](https://michalsnik.github.io/aos/)

## Getting Started

### Prerequisites

- Node.js and npm
- MetaMask browser extension
- Access to an Ethereum testnet (e.g., Polygon, Goerli)
- Infura project credentials for IPFS

### Installation

1. **Clone the repository:**
   ```bash
   git clone <repo-url>
   cd blockchainproject/Blockchain
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Configure Environment:**
   - Update your Infura Project ID and Secret in `js/App.js`.
   - Set your deployed contract address and ABI in `js/App.js`.

4. **Run the App:**
   - Open `index.html` in your browser.
   - Make sure MetaMask is connected to the correct network.

### Directory Structure

```
Blockchain/
  ├── about.html
  ├── admin.html
  ├── assets/
  ├── Contract/
  │   └── Verfication.sol
  ├── css/
  ├── delete.html
  ├── files/
  ├── index.html
  ├── js/
  ├── package.json
  ├── upload.html
  └── verify.html
```

## Usage

- **Upload:** Go to "Upload" and select a document. Confirm the transaction in MetaMask.
- **Verify:** Go to "Verify" and upload a document to check its authenticity.
- **Delete:** Go to "Delete" to remove a document hash (requires authorization).
- **Admin:** Manage exporters and view stats in the "Admin" section.

## Smart Contract Overview

See [`Contract/Verfication.sol`](Contract/Verfication.sol) for the Solidity code. Key functions:
- `add_Exporter(address, string)`
- `delete_Exporter(address)`
- `alter_Exporter(address, string)`
- `addDocHash(bytes32, string)`
- `findDocHash(bytes32)`
- `deleteHash(bytes32)`
- `getExporterInfo(address)`

## Credits

- **Developer:** Praveen Kumar (Full Stack Developer)
- **UI/UX:** Bootstrap, AOS
- **Blockchain:** Solidity, web3.js
