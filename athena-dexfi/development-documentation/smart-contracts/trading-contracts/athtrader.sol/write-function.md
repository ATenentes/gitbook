---
description: List of write functions.
---

# Write Function

External

* ````solidity
  ```solidity
  function invest(uint256 amount_, address referrer_) external
  ```
  ````
* ````solidity
  ```solidity
  function emergencyWithdraw() external
  ```
  ````
* ````solidity
  ```solidity
  function withdraw() external
  ```
  ````
* ````solidity
  ```solidity
  function harvestReward() external
  ```
  ````
* ```solidity
  function depositToken(
      uint256 _amount,
      address _module,
      address _inputToken,
      address payable _owner,
      address _witness,
      bytes calldata _data,
      bytes32 _secret
  ) external onlyTrader 
  ```
* ```solidity
  function CancelOrder(
      address _module,
      address _inputToken,
      address payable _owner,
      address _witness,
      bytes calldata _data
  ) external traderOrOwner
  ```
* ```solidity
  function lendToken(
      address _token,
      uint256 _amount
  ) external onlyTrader
  ```
* ```solidity
  function releaseLendedToken(
      address _token,
      uint256 _amount,
      bool _fullRelease
  ) external onlyTrader
  ```
* ```solidity
  function borrowToken(
      address _token,
      uint256 _amount
  ) external onlyTrader
  ```
* ```solidity
  function repayBorrowToken(
      address _token,
      uint256 _amount,
      bool _fullRepay
  ) external onlyTrader
  ```
* ```solidity
  function transferTokenToSOContract(
      address _token,
      uint256 _amount
  ) external onlyTrader
  ```
* ```solidity
  function RecoverTokenFromSOContract(
      address _token,
      uint256 _amount
  ) external onlyTrader
  ```

Public

* ````solidity
  ```solidity
  function ownableSwap(
      address router_,
      address[] memory route_,
      uint amountIn_,
      uint amountOutMin_,
      uint deadline_
  ) public onlyOwner
  ```
  ````
* ```solidity
  function swap(
      address router_,
      address[] memory route_,
      uint amountIn_,
      uint amountOutMin_,
      uint deadline_
  ) public onlyTrader
  ```

#### Internal

* ```solidity
  function internalSwap(
      address router_,
      address[] memory route_,
      uint amountIn_,
      uint amountOutMin_,
      uint deadline_
  ) internal
  ```
* ```solidity
  function calculateFee(
      uint256 surPlus_
  ) internal view returns (uint256)
  ```
*
