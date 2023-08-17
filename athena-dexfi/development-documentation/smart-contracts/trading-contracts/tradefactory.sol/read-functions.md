---
description: View functions list.
---

# Read Functions

#### internal

```
isOwner
```

* ````solidity
  ```solidity
  /**
   * * @dev view function to check msg.sender is owner
   */
  function isOwner() internal view {
      require(owner == msg.sender, "29");
  }
  ```
  ````

#### external

```solidity
tradersLength
```

* ```solidity
  /**
  * @dev returns length of traders array
  */
  function tradersLength() external view returns (uint256) {
      return traders.length;
  }
  ```

```solidity
getTraders
```

* ```solidity
  /**
  * @dev returns traders array
  */
  function getTraders() external view returns (address[] memory) {
      return traders;
  }
  ```
