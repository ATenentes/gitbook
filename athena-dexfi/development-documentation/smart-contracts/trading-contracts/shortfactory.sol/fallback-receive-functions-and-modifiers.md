---
description: Fallback, Receive functions & Modifiers
---

# Fallback, Receive functions & Modifiers

#### Modifiers

```
onlyOwner
```

* ```solidity
  modifier onlyOwner() {
      require(owner == msg.sender, "29");
      _;
  } // To check if accessed by owner
  ```

```solidity
onlyTraderFactory
```

* ```solidity
  modifier onlyTraderFactory() {
          require(traderFactory == msg.sender, "46");
          _;
      }
  ```

```solidity
OwnerOrTraderFactory
```

* ```solidity
  modifier OwnerOrTraderFactory() {
          require(owner == msg.sender || traderFactory == msg.sender, "47");
          _;
      }
  ```
