---
description: List of Variables which is used by ATHShort smart contract.
---

# Variables

Single Type Variables

* ```solidity
  address public owner;
  ```
* ```solidity
  address public traderFactory;
  ```
* ```solidity
  uint256 public borrowLimitInPer = 4000;
  ```
* ```solidity
  address[] public shorts;
  ```
*
*

Mapping variables

* ```solidity
  mapping(address => bool) public allowedLendTokens;  //map of tokens allowed to be lent
  ```
* ```solidity
  mapping(address => bool) public allowedBorrowTokens; //map of tokens allowed to be borrowed
  ```
