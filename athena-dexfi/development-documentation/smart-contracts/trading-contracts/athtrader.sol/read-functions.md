---
description: View functions list.
---

# Read Functions

#### Public

```
isFundingActive
```

* ````solidity
  ```solidity
  /**
   * @dev Returns true if funding is active
   */
  function isFundingActive() public view returns (bool) {
      return (block.timestamp >= fundingStartTime) &&
      (block.timestamp < fundingStartTime + fundingPeriod);
  }
  ```
  ````

```
isTradingActive
```

* ````solidity
  ```solidity
  /**
  * @dev Returns true if funding is active
  */
  function isFundingActive() public view returns (bool) {
  return (block.timestamp >= fundingStartTime) &&
  (block.timestamp < fundingStartTime + fundingPeriod);
  }
  ```
  ````

```solidity
isTradingActive
```

* ````solidity
  ```solidity
  /**
  * @dev Returns true if trading is active
  */
  function isTradingActive() public view returns (bool) {
  return (block.timestamp >= fundingStartTime + fundingPeriod) &&
  (block.timestamp < fundingStartTime + fundingPeriod + tradingPeriod) &&
  totalInvestment >= fundingCap;
  }
  ```
  ````

```solidity
isTradingActive
```

* ```solidity
  /**
  * @dev Returns true if trading is active
  */
  function isTradingActive() public view returns (bool) {
  return (block.timestamp >= fundingStartTime + fundingPeriod) &&
  (block.timestamp < fundingStartTime + fundingPeriod + tradingPeriod) &&
  totalInvestment >= fundingCap;
  }
  ```

```solidity
isRewardActive
```

* ```solidity
  /**
  * @return true if the contract is currently in claiming period and the funding cap is satisfied
  */
  function isRewardActive() public view returns (bool) {
  return (block.timestamp > fundingStartTime + fundingPeriod + tradingPeriod) &&
  totalInvestment >= fundingCap;
  }
  ```

```solidity
isTradedTokenConverted
```

* ```solidity
  /**
  * @dev Returns true if all traded token is converted back to participation token
  *
  */
  function isTradedTokenConverted() public view returns (bool) {
  for (uint256 i = 0; i < tradedToken.length; i++) {
      // "10 ** (IBEP20Token(tradedToken[i]).decimals().sub(4))" is equivalent to 0.0001 token
      if (IBEP20Token(tradedToken[i]).balanceOf(address(this)) > 10 ** (IBEP20Token(tradedToken[i]).decimals().sub(4))) {
          return false;
      }
  }
  return true;
  }
  ```

```solidity
isOrdersClosed
```

* ```solidity
  /**
  * @dev Returns true if all limit/stop orders are closed
  *
  */
  function isOrdersClosed() public view returns (bool) {
  for (uint256 i = 0; i < gelatoVaults.length; i++) {
      if (IBEP20Token(gelatoVaultToken[gelatoVaults[i]]).balanceOf(gelatoVaults[i]) > 0) {
          return false;
      }
  }
  return true;
  }
  ```

```solidity
isFundingActiveForAthLevel
```

* ```solidity
  /**
  * @dev Returns true if funding is active for given level
  *
  * @param level_ index of level
  */
  function isFundingActiveForAthLevel(
  uint8 level_
  ) public view returns (bool) {
  uint256 lockPeriod = fundingPeriod.div(4);

  if (level_ == 0) {
      return (block.timestamp >= fundingStartTime.add(lockPeriod.mul(3)));
  } else if (level_ == 1) {
      return (block.timestamp >= fundingStartTime.add(lockPeriod.mul(2)));
  } else if (level_ == 2) {
      return (block.timestamp >= fundingStartTime + lockPeriod);
  } else if (level_ == 3) {
      return (block.timestamp >= fundingStartTime);
  } else {
      return false;
  }
  }
  ```

#### External

```solidity
getTradedTokenList
```

* ```solidity
  /**
  * @dev Returns array of trader token
  */
  function getTradedTokenList() external view returns (address[] memory) {
  return tradedToken;
  }
  ```

#### Internal

```solidity
calculateFee
```

* ```solidity
  /**
      * @dev Returns fee on surplus amount
      *
      * @param surPlus_ surplus amount of participation tokens
      */
  function calculateFee(
      uint256 surPlus_
  ) internal view returns (uint256) {
      return (ITRADERFACTORY(traderFactory).athLevelFee(uint8(IATHLEVEL(athLevel).athLevel(msg.sender))) * surPlus_) / 100;
  }
  ```

```solidity
isOwner
```

* ```solidity
  /**
      * @dev view function to check msg.sender is owner
      */
  function isOwner() internal view {
      require(owner == msg.sender, "29");
  }
  ```

```solidity
isTrader
```

* ```solidity
  function isTrader() internal view {
          require(trader == msg.sender, "30");
      }
  ```

```solidity
isTraderOrOwner
```

* ```solidity
  function isTraderOrOwner() internal view {
          require(trader == msg.sender || owner == msg.sender, "32");
      }
  ```
