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
