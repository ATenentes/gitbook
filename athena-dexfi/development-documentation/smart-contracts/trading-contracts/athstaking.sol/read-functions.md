---
description: View functions list.
---

# Read Functions

#### External

```
athLevel
```

* ```solidity
  /**
  	 * @dev Returns ATH level of given address
  	 *
  	 * @notice returns zero in case of locking period is over
  	 * @param user_ address of staker
  	 */
  function athLevel(address user_) external view returns(uint256 level) {
      if(block.timestamp - athBalance[user_].lastUpdated > lockingPeriodInSeconds) {
          level = 0;
      } else {
          level = athBalance[user_].level;
      }
  }
  ```

#### Internal

```solidity
calculateFee
```

* ````solidity
  ```solidity
  /**
  * @dev Returns fee on surplus amount
  *
  * @param surPlus_ surplus amount of participation tokens
  */
  function calculateFee(uint256 surPlus_) internal view returns (uint256) {
  return (ITRADERFACTORY(traderFactory).athLevelFee(uint8(IATHLEVEL(athLevel).athLevel(msg.sender))) * surPlus_) / 100;
  }
  ```
  ````

```solidity
isOwner
```

* <pre class="language-solidity"><code class="lang-solidity">/**
  * @dev view function to check msg.sender is owner
  */
  function isOwner() internal view {
  <strong>require(owner == msg.sender, "29");
  </strong>}
  </code></pre>

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
