# Types-of-Function
# Description
this project, you will write a smart contract to create your own ERC20 token and deploy it using HardHat or Remix. Once deployed, you should be able to interact with it for your walk-through video. From your chosen tool, the contract owner should be able to mint tokens to a provided address and any user should be able to burn and transfer tokens.

#Executing the program
// SPDX-License-Identifier: Apache-2.0
pragma solidity ^0.8.0;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";

contract MyToken is ERC20 {
    address public owner;

    constructor(string memory _name, string memory _symbol,uint256 initialSupply) ERC20(_name, _symbol) {
     _mint (msg.sender, initialSupply);
     owner = msg.sender;
    }

    modifier onlyOwner() {
        require(msg.sender == owner, "Only the owner can call this function");
        _;


  The Solidity code defines a smart contract called MyToken, an ERC20 token, using the OpenZeppelin library for standardized and secure implementations of ERC20 token functionality. and this contract sets the deploying address to be the owner.
It only allows minting new tokens by calling the mint function by the owner.
Burning: With the burn function, any token holder is capable of burning their own tokens.
It has the standard ERC20 functions of transfer and transferFrom, supplemented by conditions of prohibition of transfers to the zero address.
It is a smart contract that uses OpenZeppelin's implementation of the ERC20, leveraging its safety and compliance with the ERC20 standard, adding user-defined functionalities around minting, burning, and ownership restrictions.

# Author
Metacrafter Anazel

# License
This project is licensed under the MIT License
