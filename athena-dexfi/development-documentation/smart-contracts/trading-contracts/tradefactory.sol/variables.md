---
description: List of Variables which is used by ATHShort smart contract.
---

# Variables

Single Type Variables

* ```solidity
  uint8 public traderFee = 50; // fee that goes to trader in %, example 50% = 50
  ```
* ```solidity
  uint public traderDeploymentFee = 0.1 ether; // fee to be paid for creating a tradingContract
  ```
* ```solidity
  address[] public traders; // array of all created tradingContracts
  ```
* ```solidity
  address public owner; // address of owner
  ```
* ```solidity
  address public athLevel; // address of AthStaking contract, used for checking level of users
  ```
* ```solidity
  address public shortFactory; // address of factory of shorts, independent because of space limitations
  ```

Mapping variables

* ```solidity
  /**
  * @dev returns the index of the trader in the traders array, mind that actual index is index - 1 because of the 0 default value
  */
  mapping(address => uint256) public traderIndex;
  ```
* ```solidity
  /**
  * @dev mapping of allowedTokens for trading
  */
  mapping(address => bool) public AllowedTokens;
  ```
* ```solidity
  /**
  * @dev Returns investor's fee in percentage  of given level
   */
  mapping(uint8 => uint8) public athLevelFee;
  ```
* ```solidity
  /**
  * @dev Returns referrerFee in percentage  of given level
   */
  mapping(uint8 => uint8) public referrerFeeFromLevel;
  ```
