---
description: List of write functions.
---

# Write Function

External

* ````solidity
  ```solidity
  function setShortFactory(address _shortFactory) external onlyOwner
  ```
  ````
* ````solidity
  ```solidity
  function lendToken(address _token, uint256 _amount) external traderOrTraderContract nonReentrant
  ```
  ````
* ````solidity
  ```solidity
  function releaseLendedToken(address _token, uint256 _amount, bool _fullRelease) external traderOrTraderContract nonReentrant
  ```
  ````
* ````solidity
  ```solidity
  function repayBorrowToken(address _token, uint256 _amount, bool _fullRepay) external traderOrTraderContract nonReentrant
  ```
  ````
* ````solidity
  ```solidity
  function transferTokenToTraderContract(address _token, uint256 _amount) external traderOrTraderContract nonReentrant
  ```
  ````
* ````solidity
  ```solidity
  function whitelistLendToken(address[] calldata _token) external traderOrOwner
  ```
  ````
* ````solidity
  ```solidity
  function delistLendToken(address _token) external traderOrOwner
  ```
  ````
* ````solidity
  ```solidity
  function whitelistBorrowToken(address[] calldata _token) external traderOrOwner
  ```
  ````
* ````solidity
  ```solidity
  function delistBorrowToken(address _token) external traderOrOwner
  ```
  ````
* ````solidity
  ```solidity
  function updateBorrowLimit(uint256 _borrowLimitInPer) external onlyOwner
  ```
  ````
* ````solidity
  ```solidity
  function updateTraderAddress(address _addr) external onlyOwner
  ```
  ````
* ````solidity
  ```solidity
  function updateTraderContractAddress(address _addr) external onlyOwner
  ```
  ````

Public

* ````solidity
  ```solidity
  function claimXVSToken() public traderOrTraderContract
  ```
  ````
