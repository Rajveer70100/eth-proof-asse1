# MyToken Smart Contract

This repository contains a Solidity smart contract for a simple ERC-20 token named **JUNK** with the symbol **JNK**. The contract includes basic functionalities such as minting and burning tokens.

## Requirements

The contract meets the following requirements:

1. **Public Variables**: Stores the details about the token (Token Name, Token Abbrv., Total Supply).
2. **Mapping of Addresses to Balances**: Keeps track of each address's balance.
3. **Mint Function**: Increases the total supply and the balance of the specified address.
4. **Burn Function**: Decreases the total supply and the balance of the specified address, with a check to ensure sufficient balance.

## Contract Details

### Public Variables

- **name**: The name of the token (JUNK).
- **symbol**: The abbreviation of the token (JNK).
- **totalSupply**: The total supply of tokens.

### Mapping

- **balances**: A mapping from addresses to their respective token balances.

### Functions

#### Mint

Increases the total supply of tokens and the balance of the specified address.

```solidity
function mint(address _to, uint _value) public {
    totalSupply += _value;
    balances[_to] += _value;
}
function burn(address _from, uint _value) public {
    require(balances[_from] >= _value, "Insufficient balance to burn");
    totalSupply -= _value;
    balances[_from] -= _value;
}

You can save this content as `README.md` in your GitHub repository to provide an overview and instructions for your smart contract.
