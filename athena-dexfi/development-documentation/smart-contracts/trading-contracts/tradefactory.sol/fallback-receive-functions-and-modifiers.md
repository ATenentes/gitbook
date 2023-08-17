---
description: Fallback, Receive functions & Modifiers
---

# Fallback, Receive functions & Modifiers

#### Modifiers

```
onlyOwner
```

* ```solidity
  // To check if accessed by an owner
  modifier onlyOwner() {
      isOwner();
      _;
  }
  ```
