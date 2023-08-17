---
description: Fallback, Receive functions & Modifiers
---

# Fallback, Receive functions & Modifiers

#### Modifiers

```
onlyOwner
```

* ````solidity
  ```solidity
  // To check if accessed by an owner
      modifier onlyOwner() {
          isOwner();
          _;
      }

  ```
  ````

```
onlyTrader
```

* ````solidity
  ```solidity
  // To check if accessed by a trader
      modifier onlyTrader() {
          isTrader();
          _;
      }
  ```
  ````

```solidity
traderOrOwner
```

* ```solidity
  // To check if accessed by an owner or a tarder
  modifier traderOrOwner() {
      isTraderOrOwner();
      _;
  }
  ```

