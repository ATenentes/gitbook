---
description: Fallback, Receive functions & Modifiers
---

# Fallback, Receive functions & Modifiers

#### Fallback

* ````solidity
  ```solidity
  // Fallback function is called when msg.data is not empty
  fallback() external payable {}
  ```
  ````

Receive

* ````solidity
  ```solidity
  // Function to receive Ether. msg.data must be empty
  receive() external payable {}
  ```
  ````

#### Modifiers

```
traderOrTraderContract
```

* ````solidity
  ```solidity
  // To check if accessed by a trader or a trader Contract
  modifier traderOrTraderContract() {
      internalTraderOrTraderContract();
      _;
  }
  ```
  ````

```
traderOrOwner
```

* <pre class="language-solidity"><code class="lang-solidity">```solidity
  modifier traderOrOwner() {
      require(msg.sender == trader || msg.sender == owner(), "32");
  <strong>    _;
  </strong>}
  ```
  </code></pre>

