# Jaguar Token Contract
- This repository contains the Solidity code for the Jaguar token, an ERC20 compliant token with additional functionality for minting and burning tokens, and a customized transfer function. The contract uses OpenZeppelin libraries to ensure security and standard compliance.

## Overview
- The Jaguar contract is an implementation of the ERC20 standard, with added capabilities for the contract owner to mint new tokens and for token holders to burn their tokens. The contract also overrides the default transfer function to include a custom implementation.

## Description
- The Jaguar contract extends the following OpenZeppelin contracts:

- ERC20: Implements the ERC20 token standard.
- Ownable: Provides basic authorization control functions to simplify the implementation of user permissions.
## The contract uses these functionalities to provide a robust and secure token with the following features:

- Minting: The contract owner can mint new tokens to a specified address.
- Burning: Any token holder can burn a specified amount of their tokens.
- Transfer: The default ERC20 transfer function is overridden to provide a custom implementation.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., Avalanch_03.sol). Copy and paste the following code into the file:

```solidity
//SPDX-License-Identifier:MIT
pragma solidity ^0.8.0;

import "@openzeppelin/contracts@5.0.1/token/ERC20/ERC20.sol";
import "@openzeppelin/contracts@5.0.1/access/Ownable.sol";


contract Jaguar is ERC20, Ownable {
    constructor(address initialOwner)
        ERC20("Jaguar", "JR")
        Ownable(initialOwner)
      
    {}

    function mint(address jaguar_address, uint256 amount) public onlyOwner {
        _mint(jaguar_address, amount);
    }

    function burn(uint256 jaguar_value) public returns(bool) {
        _burn(msg.sender,jaguar_value);
        return true;
    }   
    function transfer(address jaguar_address, uint256 amount) public override returns(bool){
        _transfer(msg.sender, jaguar_address, amount);
        return true;
    }    
}

```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.4" (or another compatible version), and then click on the "Compile Avalanch_03.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "Avalanch_03" contract from the dropdown menu, and then click on the "Deploy" button.


## Authors

shreyas s  
[shreyas1665@gmail.com]


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
