---
description: Fallback, Receive functions & Modifiers
---

# Fallback, Receive functions & Modifiers

#### Modifiers

```
publicSaleActive
```

* ````solidity
  ```solidity
  modifier publicSaleActive() {
      require(
          block.timestamp >= startTime,
          "Public sale is not yet activated"
      );
      _;
  }
  ```
  ````

```
publicSaleEnded
```

* ````solidity
  ```solidity
  modifier publicSaleEnded() {
  require((block.timestamp > endTime || availableTokens == 0), "Public sale not yet ended");
  _;
  }
  ```
  ````

```solidity
canClaim
```

* ````solidity
  ```solidity
  modifier canClaim() {
  require(block.timestamp >= releaseTime, "Please wait until release time for claiming tokens");
  _;
  }
  ```
  ````
