---
description: List of write functions.
---

# Write Function

External

* ````solidity
  ```solidity
  function transferOwnership(address newOwner_) external onlyOwner
  ```
  ````
* ```solidity
  function setDepostFee(uint8 fee_) external onlyOwner
  ```
* ```solidity
  function setLockingPeriod(uint32 lockingPeriod_) external onlyOwner
  ```
* ```solidity
  function deposit(uint256 amount_, uint8 level_) external
  ```
* ```solidity
  function withDraw() external
  ```
