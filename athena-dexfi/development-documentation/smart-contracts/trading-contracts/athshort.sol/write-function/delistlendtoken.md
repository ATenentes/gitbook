---
description: function to remove from whitelist allowed token to lend on venus
---

# delistLendToken

````solidity
```solidity
/**
 *
 * @notice restricted function, should be called by owner or trader
 * @param _token venus token address which is not allowed to be lended on venus
 */
function delistLendToken(address _token) external traderOrOwner {
    require(block.timestamp <= START_TIME, "37");
    require(_token != address(0x0), "04");
    require(isLendToken[_token], "02");

    venusComptroller.exitMarket(_token);
    IBEP20Token(underlying[_token]).approve(_token, 0);
    isLendToken[_token] = false;

    emit DeListToken(_token, underlying[_token]);

    reverseUnderlying[underlying[_token]] = address(0x0);
    underlying[_token] = address(0x0);
}
```
````
