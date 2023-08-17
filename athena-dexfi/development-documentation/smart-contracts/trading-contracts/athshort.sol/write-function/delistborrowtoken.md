---
description: function to removed from whitelist allowed token to borrowed from venus
---

# delistBorrowToken

````solidity
```solidity
/**
 *
 * @notice restricted function, should be called by owner or trader
 * @param _token venus token address which is not allowed to be borrowed from venus
 */
function delistBorrowToken(address _token) external traderOrOwner {
    require(block.timestamp <= START_TIME, "37");
    require(_token != address(0x0), "04");
    require(isBorrowToken[_token], "02");

    if (_token != vBNBToken) {
        IBEP20Token(underlying[_token]).approve(_token, 0);
    }
    isBorrowToken[_token] = false;

    emit DeListToken(_token, underlying[_token]);

    reverseUnderlying[underlying[_token]] = address(0x0);
    underlying[_token] = address(0x0);
}
```
````
