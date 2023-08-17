---
description: List of Variables which is used by ATHShort smart contract.
---

# Variables

Single Type Variables

* ```solidity
  address public owner; // Address of AthStaking owner
  ```
* ```solidity
  address public immutable athToken; // Address of ATH token contract
  ```
* ```solidity
  address public immutable treasury; // Address of treasury
  ```
* ```solidity
  uint8 public immutable levels; // Number of staking levels
  ```
* ```solidity
  uint8 public depositFee; // Deposit fee defined in terms of percentage
  ```
* ```solidity
  uint32 public lockingPeriodInSeconds; // Locking period defined in terms of seconds
  ```

Mapping variables

* ```solidity
  mapping(address => AthData) public athBalance; //Returns staking data for given address
  ```
* ```solidity
  mapping(uint8 => uint256) public minAthRequired; // Returns minimum ATH token required for given level
  ```
