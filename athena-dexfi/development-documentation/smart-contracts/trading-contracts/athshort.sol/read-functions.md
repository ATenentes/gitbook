---
description: View functions list.
---

# Read Functions

#### Internal

```
internalTraderOrTraderContract
```

* ````solidity
  ```solidity
  /**
  * @dev internal function To check if accessed by a trader or a trader Contract to save contract size
  */
  function internalTraderOrTraderContract() internal view {
      require(trader == msg.sender || traderContract == msg.sender, "Error Msg");
  }
  ```
  ````

