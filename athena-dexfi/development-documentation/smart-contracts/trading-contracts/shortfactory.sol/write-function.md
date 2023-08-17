---
description: List of write functions.
---

# Write Function

public

* ```solidity
  function setTraderFactory(address traderFactory_) public onlyOwner
  ```
* ```solidity
  function setBorrowLimitInPer(uint256 borrowLimitInPer_) public onlyOwner
  ```
* ```solidity
  function addAllowedLendToken(address[] memory tokens_) public onlyOwner
  ```
* ```solidity
  function removeAllowedLendToken(address[] memory tokens_) public onlyOwner
  ```
* ```solidity

  function addAllowedBorrowToken(address[] memory tokens_) public onlyOwner
  ```
* ```solidity
  function removeAllowedBorrowToken(address[] memory tokens_) public onlyOwner
  ```
* ```solidity
  function setOwner(address owner_) public onlyOwner
  ```
* ```solidity
  function removeShortByIndex(uint256 index_) public onlyOwner
  ```
* ```solidity
  function removeShortByAddress(address[] memory shorts_) public onlyOwner
  ```
* ```solidity
  function createShort(uint256 _startTime,
          address _traderContractAddress,
          address _traderAddress,
          address _participationTokenAddress) public OwnerOrTraderFactory returns (address)
  ```
