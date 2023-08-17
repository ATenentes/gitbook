---
description: function to update borrow limit in percentage
---

# updateBorrowLimit

````solidity
```solidity
/**
*
* @notice restricted function, should be called by owner
* @param _borrowLimitInPer allowed borrow limit in percentage (50% means 5000)
*/
function updateBorrowLimit(uint256 _borrowLimitInPer) external onlyOwner {
   require(block.timestamp <= START_TIME, "39");
   require(_borrowLimitInPer <= 7000, "40");

   borrowLimitInPer = _borrowLimitInPer;
}
```
````
