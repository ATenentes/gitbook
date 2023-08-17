---
description: function to claim XVS rewarded due to borrow/lend on venus platform
---

# claimXVSToken

````solidity
```solidity
/**
* @notice restricted function, should be called by trader or trader contract only
*/
function claimXVSToken() public traderOrTraderContract {
venusComptroller.claimVenus(address(this), venusComptroller.getAssetsIn(address(this)));
}
```
````
