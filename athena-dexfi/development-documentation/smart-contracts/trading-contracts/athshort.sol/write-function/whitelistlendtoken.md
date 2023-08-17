---
description: function to whitelist allowed token to lend on venus
---

# whitelistLendToken

````solidity
```solidity
/**
 * @notice restricted function, should be called by owner or trader
 * @param _token array of venus token address which is allowed to be lended on venus
 */
function whitelistLendToken(address[] calldata _token) external traderOrOwner {
    require(block.timestamp <= START_TIME, "37");
    require(_token.length > 0, "04");

    for (uint8 i = 0; i < _token.length; i++) {
        require(ISHORTFACTORY(shortFactory).allowedLendTokens(_token[i]), "02");
    }

    venusComptroller.enterMarkets(_token);
    address underlyingToken;
    for (uint8 i = 0; i < _token.length; i++) {
        underlyingToken = IVenusToken(_token[i]).underlying();
        IBEP20Token(underlyingToken).approve(_token[i], MAX_INT);
        isLendToken[_token[i]] = true;
        underlying[_token[i]] = underlyingToken;
        reverseUnderlying[underlyingToken] = _token[i];

        emit WhiteListToken(_token[i], underlyingToken);
    }
}
```
````
