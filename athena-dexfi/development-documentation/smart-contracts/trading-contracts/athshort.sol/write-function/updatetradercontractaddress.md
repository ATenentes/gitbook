---
description: function to update trader contract address
---

# updateTraderContractAddress

````solidity
```solidity
/**
*
* @notice restricted function, should be called by owner
* @param _addr address of trader contract
*/
function updateTraderContractAddress(address _addr) external onlyOwner {
   require(_addr != address(0x0), "04");

   traderContract = _addr;
}
```
````
