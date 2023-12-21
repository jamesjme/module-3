
# Token Contract

This Solidity contract, named "Token," is a basic ERC-20 token implementation. ERC-20 is a widely used standard on the Ethereum blockchain for fungible tokens.

## Overview

The Token contract includes the following functionalities:

- Minting new tokens: The owner can create and send new tokens to a designated address.
- Burning tokens: The owner can burn (destroy) a specified amount of tokens, reducing the total supply.
- Transferring tokens: Users can transfer tokens to other addresses.

## Prerequisites

- Solidity Compiler: Ensure that you have the necessary Solidity compiler installed to compile the contract.
- Ethereum Development Environment: Set up an Ethereum development environment for testing and deploying the contract.

## Deployment

1. Deploy the contract on the Ethereum blockchain, specifying the token name and symbol.

```solidity
constructor(string memory name, string memory symbol) ERC20(name, symbol) {}
```

2. Mint Tokens: The owner can use the `mint` function to create and send tokens to a specific address.

```solidity
function mint(address awardee, uint256 consignment) external onlyOwner {
    _mint(awardee, consignment);
}
```

3. Burn Tokens: The owner can use the `burn` function to destroy a specified amount of tokens.

```solidity
function burn(uint256 consignment) public override {
    _burn(msg.sender, consignment);
}
```

4. Transfer Tokens: Users can use the standard `transfer` function to send tokens to another address.

```solidity
function transfer(address awardee, uint256 consignment) public virtual override returns (bool) {
    _transfer(_msgSender(), awardee, consignment);
    return true;
}
```

## Usage

1. Deploy the contract on the Ethereum blockchain.
2. Mint tokens using the `mint` function.
3. Burn tokens using the `burn` function.
4. Transfer tokens using the `transfer` function.

