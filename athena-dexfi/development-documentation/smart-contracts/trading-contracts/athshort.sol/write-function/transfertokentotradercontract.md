---
description: function to transfer token from short order contract to trader contract
---

# transferTokenToTraderContract

````solidity
```solidity
/**
*
* @notice restricted function, should be called by trader or trader contract only
* @param _token address of ERC20 token address
* @param _amount amount of ERC20 token need to be transfered
*/
function transferTokenToTraderContract(address _token, uint256 _amount) external traderOrTraderContract nonReentrant {
   require(_token != address(0x0) &&
       _amount <= IBEP20Token(_token).balanceOf(address(this)), "04");

   IBEP20Token(_token).transfer(traderContract, _amount);
}
```
````
