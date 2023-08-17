---
description: setshortFactory address
---

# setShortFactory

```solidity
/**
* @param _shortFactory address of shortFactory
*/
function setShortFactory(address _shortFactory) external onlyOwner {
    shortFactory = _shortFactory;
}
```
