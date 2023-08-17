---
description: List of write functions.
---

# Write Function

public

* ```solidity
  function setShortFactory(address shortFactory_) external onlyOwner
  ```
* ```solidity
  function setAthLevel(address athLevel_) external onlyOwner
  ```
* ```solidity
  function addAllowedToken(address[] memory tokens_) external onlyOwner
  ```
* ```solidity
  function removeAllowedToken(address[] memory tokens_) external onlyOwner
  ```
* ```solidity
  function removeTraderByAddress(address[] memory tradersToRemove_) external onlyOwner
  ```
* ```solidity
  function setTraderFee(uint8 fee_) external onlyOwner
  ```
* ```solidity
  function setTraderDeploymentFee(uint fee_) external onlyOwner
  ```
* ```solidity
  function setAthLevelFee(
          uint8[] memory level_,
          uint8[] memory fee_
      ) external onlyOwner
  ```
* ```solidity
  function setReferrerFeeFromLevel(
          uint8[] memory level_,
          uint8[] memory fee_
      ) external onlyOwner
  ```
* ```solidity
  function createTrader(address traderEOA_) payable external returns (AthTrader)
  ```
* ```solidity
  function createTraderByOwner(address traderEOA_) external onlyOwner returns (AthTrader) 
  ```
* ```solidity
  function addShortToTrader(address traderContract_) external
  ```
* ```solidity
  function transferOwnership(address newOwner_) external onlyOwner
  ```

#### Public

* ```solidity
  function removeTraderByIndex(uint256 index_) public onlyOwner
  ```

#### Internal

* ```solidity
  function _deployTrader(address traderEOA_) internal returns (AthTrader)
  ```
