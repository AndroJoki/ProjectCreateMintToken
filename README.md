# Project: Create and Mint Token

This Solidity program is about ERC20 tokens. The purpose of this program is to help understand ERC20 tokens and be able to mint, transfer, and burn tokens.

## Description

This program is a Solidity-based smart contract designed to help developers understand and utilize the ERC20 token standard. It includes functions to mint, transfer, and burn tokens, showcasing how these operations can be performed within the framework of the ERC20 standard. This contract serves as a foundational example for developers looking to grasp the basic mechanisms of ERC20 tokens, providing a stepping stone for more advanced token development and integration in decentralized applications.

## Getting Started

### Creating the program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., myERCToken.sol). Copy and paste the following code into the file:
```javascript
// SPDX-License-Identifier: MIT
// Compatible with OpenZeppelin Contracts ^5.0.0
pragma solidity ^0.8.20;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";
import "@openzeppelin/contracts/token/ERC20/extensions/ERC20Burnable.sol";

contract Andro is ERC20, ERC20Burnable {
    address public owner;

    constructor(address initialOwner)
        ERC20("Andro", "DRO")
    {
        owner = initialOwner;
    }

    modifier onlyOwner() {
        require(msg.sender == owner, "Only owner can perform this action");
        _;
    }

    function mint(address to, uint256 amount) public onlyOwner {
        _mint(to, amount);
    }
}
```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.26" (or another compatible version), and then click on the "Compile myERCToken.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "Andro" contract from the dropdown menu, and then input an account address to the initialOwner input field then click on the "Deploy" button.

Once the contract is deployed, you can scroll down to see the deployed contract in the "Deployed/Unpinned Contracts" section. 

### Executing the program

To mint tokens, click on the "Andro" contract in the left-hand sidebar in the "Deployed/Unpinned Contracts" section, and then click on the "mint" function. Next, input the address of an account in the _address textfield and the amount of tokens to mint in the _value textfield. Finally, click on the "transact" button to execute the function and mint tokens on the account that was inputted. The mint function will only work if the owner was the one who executed it.

To transfer tokens to another account, click on the "Andro" contract in the left-hand sidebar in the "Deployed/Unpinned Contracts" section, and then click on the "transfer" function. Next, input the address of an account in the _address textfield and the amount of tokens to transfer your tokens in the _value textfield. Finally, click on the "transact" button to execute the function and transfer tokens to the account that was inputted.

To burn your tokens, click on the "Andro" contract in the left-hand sidebar in the "Deployed/Unpinned Contracts" section, and then click on the "burn" function. Next, input the amount of tokens to burn in the _value textfield. Finally, click on the "transact" button to execute the function and burn your tokens.

To check the balance or amount of tokens that an account has, click on the "Andro" contract in the left-hand sidebar in the "Deployed/Unpinned Contracts" section, and then click on the "balanceOf" function. Next, input the address of an account in the address textfield. Finally, click on the "call" button to execute the function and the amount of tokens of the account that was inputted will be displayed.

## Authors

Metacrafter napjoquino

## License

This project is licensed under the MIT License - see the LICENSE.md file for details
