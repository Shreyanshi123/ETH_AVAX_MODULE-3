# PokemonToken Contract
The **PokemonToken** contract has smart contract implemented on the Ethereum blockchain. It allows users to create and manage tokens with the standard functionalities of mint,burn,using lastMintTime, paused,unpaused and many others.
## Features
**Token Standard**
  -The contract implements a custom ERC-721-like token standard with additional functionalities.

- **SafeMath**
    - The contract uses SafeMath library to prevent overflow/underflow vulnerabilities in arithmetic operations.

- **Card Struct**
    - Users can define a struct "Card" to represent a Pokemon card with various attributes like "pokemonName," "cardId," "attackLevel," "defenseLevel," and "pokemonType."

- **Card Creation**
    - Allows the contract owner to create new Pokemon cards by calling the "createCard" function.

- **Token Minting**
    - The contract owner can mint new tokens by calling the "mint" function. Tokens are minted based on the time elapsed since the last minting.

- **Tokens Burning**
    - The contract owner can create new tokens and assign them to any address using the `mint` function.

- **Burn Tokens**
    -Users can burn tokens by calling the "burn" function, which reduces their balance and total supply based on the elapsed time since the last minting.

- **Time-Locked Transfers**
    - Provides time-lock functionality for token transfers with the "timelockTransfer" and "claimTimelockedTransfer" functions.
      
- **Transfer Functions**
    - Standard token transfer functions "transfer" and "transferFrom" to transfer ownership of tokens between accounts.

- **Approval Functions**
    - Allows token owners to approve and manage operator approval for transferring tokens on their behalf.

- **Whitelisting**
    - The contract owner can add and remove addresses to/from a whitelist, ensuring specific accounts have specific privileges.

- **Pausing Functionality**
    - The contract owner can pause and unpause token transfers using the "pause" and "unpause" functions, respectively.

- **Ownership Tracking**
    - Maps token IDs to their respective owners and token approvals using various mapping structures.
      
- **Events**
    - Emits events for token transfers, approvals, and token burning.
 

## Usage

-**Contract Deployment**

Deploy the PokemonToken contract with the desired tokensPerSecond rate.
The contract creator will become the contract owner, who has special privileges.

-**Create a New Card**

Only the contract owner can create new Pokemon cards.
Use the createCard function to add a new card to the contract.
Provide the card's name, attack level, and defense level as inputs.
This will mint a new card with a unique cardId.

-**View Card Details**

Use the getCardDetails function to view the details of a specific card.
Pass the cardId as an argument to get the card's name, attack level, and defense level.

-**Mint Tokens**

Only the contract owner can mint new tokens to their own balance.
Call the mint function to mint tokens based on the tokensPerSecond rate.
Tokens will be credited to the owner's balance.

-**Burn Tokens**

Any token holder can burn their tokens.
Call the burn function to burn tokens based on the tokensPerSecond rate.
The burned tokens will be subtracted from the sender's balance and total supply.

-**Pause and Unpause Token Transfers**

The contract owner can pause and unpause token transfers.
Use the pause and unpause functions for this purpose.
When paused, token transfers will be disabled.

-**Whitelist Management**

The contract owner can add or remove addresses to/from the whitelist.
Whitelisted accounts can perform token transfers.
Use the addToWhitelist and removeFromWhitelist functions for this.

-**Timelock Token Transfer**

A token holder can timelock a specific token transfer.
Call the timelockTransfer function with the tokenId and desired unlockTime.
The token will be locked until the specified unlockTime.

-**Claim Timelocked Transfer**

After a timelock is set, the token holder can claim the timelocked transfer.
Use the claimTimelockedTransfer function with the tokenId to release the token.

-**Token Transfers**

Token holders can transfer their tokens to other addresses.
Use the transfer function to transfer tokens to a specified address.
The token owner must be the sender of the transfer.

-**Token Approvals and Operator Approvals**

Token holders can approve other addresses to manage their tokens.
Use the approve function to give approval to an address for a specific token.
Use the setApprovalForAll function to approve an operator to manage all tokens.

-**Events**
The contract emits various events for important actions, such as Transfer, Approval, and ApprovalForAll.
These events can be used to track token transfers and approvals.

## License
This project is licensed under the MIT License - see the LICENSE.md file for details
