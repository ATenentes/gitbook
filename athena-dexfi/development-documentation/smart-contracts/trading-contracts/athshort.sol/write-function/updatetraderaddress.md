---
description: function to update trader address
---

# updateTraderAddress

````solidity
```solidity
/**
*
* @notice restricted function, should be called by owner
* @param _addr address of trader wallet
*/
function updateTraderAddress(address _addr) external onlyOwner {
   require(_addr != address(0x0), "04");

   trader = _addr;
}
```
````
