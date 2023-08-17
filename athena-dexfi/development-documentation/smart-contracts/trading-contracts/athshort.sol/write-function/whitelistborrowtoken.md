---
description: function to whitelist allowed token to borrowed from venus
---

# whitelistBorrowToken

````solidity
```solidity
/**
* @notice restricted function, should be called by owner or trader
* @param _token varray of venus token address which is allowed to be borrowed from venus
*/
function whitelistBorrowToken(address[] calldata _token) external traderOrOwner {
require(block.timestamp <= START_TIME, "37");
require(_token.length > 0, "04");

for (uint8 i = 0; i < _token.length; i++) {
    require(ISHORTFACTORY(shortFactory).allowedBorrowTokens(_token[i]), "02");
}

address underlyingToken;
for (uint8 i = 0; i < _token.length; i++) {
    if (_token[i] != vBNBToken) {
        underlyingToken = IVenusToken(_token[i]).underlying();
        IBEP20Token(underlyingToken).approve(_token[i], MAX_INT);
    } else {
        underlyingToken = wbnb;
    }

    isBorrowToken[_token[i]] = true;
    underlying[_token[i]] = underlyingToken;
    reverseUnderlying[underlyingToken] = _token[i];

    emit WhiteListToken(_token[i], underlyingToken);
}
}
```
````
