# Prince of Persia Coin (POP) Token

Prince of Persia Coin (POP) is an ERC20-compliant token deployed on the Ethereum blockchain. It allows for the minting, burning, and transfer of tokens within the Ethereum ecosystem.

## Overview

Prince of Persia Coin (POP) is a decentralized digital currency that provides users with various functionalities for interacting with the Ethereum network. It is based on the ERC20 standard and inherits functionalities from the OpenZeppelin libraries.

## Features

- **Minting**: The contract owner can mint new tokens and distribute them to specified addresses.
- **Burning**: Tokens can be burned by the owner, reducing the total supply.
- **Transfer**: Users can transfer tokens to other Ethereum addresses.

## Getting Started

To interact with Prince of Persia Coin (POP) tokens, you can use Ethereum wallets or blockchain explorers that support ERC20 tokens. Here's how you can get started:

1. **Obtain Wallet**: Get an Ethereum wallet that supports ERC20 tokens such as MetaMask, Trust Wallet, or MyEtherWallet.
2. **Add POP Token**: Add Prince of Persia Coin (POP) token to your wallet using the contract address.
3. **Interact**: You can now send, receive, and view your POP token balance using your Ethereum wallet.

## Contract Details

- **Name**: Prince of Persia Coin
- **Symbol**: POP
- **Decimals**: 18
- **Network**: Ethereum Mainnet

## Usage

### Mint Tokens

The contract owner can mint new tokens and distribute them to specified addresses.

```solidity
function mintTokens(address to, uint256 amount) public onlyOwner {
    require(to != address(0), "Invalid address");
    require(amount > 0, "Invalid amount");
    _mint(to, amount);
}
```

### Burn Tokens

Tokens can be burned by the owner, reducing the total supply.

```solidity
function burnTokens(address from, uint256 amount) public onlyOwner {
    require(from != address(0), "Invalid address");
    require(balanceOf(from) >= amount, "Insufficient balance");
    _burn(from, amount);
}
```

### Transfer Tokens

Users can transfer tokens to other Ethereum addresses.

```solidity
function transfer(address to, uint256 amount) public override returns (bool) {
    _transfer(msg.sender, to, amount);
    return true;
}
```

## License

This project is licensed under the MIT License.
