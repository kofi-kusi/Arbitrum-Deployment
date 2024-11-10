# Arbitrum-Deployment
In this project i learnt how to deploy to Arbitrum (Layer 2) using the Arbitrum Sepolia Testnet.

## Requirements
- You must have a wallet installed e.g MetaMask.

## Step 1: Connect MetaMask to Arbitrum Sepolia
- I opened MetaMask and clicked on the top-left conner for the **network dropdown**.
- Clicked on **Add a custom network**.
- I entered the Arbitrum Sepolia configuration by follows;
    - Network Name: Arbitrum Sepolia
    - New RPC URL: `https://sepolia-rollup.arbitrum.io/rpc`
    - Chain ID: 421614
    - Currency Symbol: ETH
    - Block Explorer URL: `https://sepolia-explorer.arbitrum.io/`
    - Clicked **Save** and i saw that the **Arbitrum Sepolia** was added to my networks.

## Step 2: Getting Arbitrum Sepolia ETH
### Failed Method
I tried to get some tokens form [Chainlink Faucet](https://faucets.chain.link/arbitrum-sepolia) but i didn't work because to get the native token, i must hold at leat 1 LINK on the Ethereum Mainnet.

### Worked
I moved to [Alchemy Faucet](https://www.alchemy.com/faucets/arbitrum-sepolia), there too they said ...
    ```
    To prevent bots and abuse, this faucet requires a minimum Arbitrum mainnet balance of 0.001 ETH on the wallet address being used.
    ``` which i was having :), so i entered my wallet address and the token was sent to it.

# Deployed my contract on Arbitrum with Remix.
## Step 3: Setting up the evironment.
- I created a new blank workspace and named it **Arbitrum Demo**.
- I then created a new solidity file which i named `HelloArbitrum.sol`.
- I then wrote my smart contract in it;
  ```solidity
  // SPDX-License-Identifier: MIT
  pragma solidity ^0.8.25;
  
  contract HelloArbitrum {
      string public message;

      // Constructor to initialize the contract with a message
      constructor(string memory _message) {
          message = _message;
      }
  
      // Function to update the message
      function updateMessage(string memory _newMessage) public {
          message = _newMessage;
      }
  }
  ```
- And compiled the contract.

## Step 4: Connected my MetaMask to Remix
- I opened my wallet and switched the network to **Arbitrum Sepolia**.
- Clicked the **Deploy & Run Transaction** tap.
- Selected **Injected Provider-MetaMask** under the **Environment**.
- MetaMask prompted me to approve the connection, i clicked `connect`.

## Deployed the contract to Arbitrum Sepolia
- Deploy the contraction by passing `"Hello, Arbitrum!" as an argument to the constructor function.
- MetaMask pop up for confirmation, so  i clicked `confirm`.
- I then passed an argument `"Welcome to Layer 2"` to the `updateMessage()` function and confirmed the transaction again.

## Viewing my tracsaction on Arbiscan
- headed to [Arbiscan](https://sepolia.arbiscan.io/) and inputed my *transaction hash*
- and i saw all the details of my transactions.

