---
description: Lend token Venus Platform
---

# lendToken

````solidity
```solidity
/**
 *
 * @notice restricted function, should be called by trader or trader contract only
 * @param _token address of venus token address
 * @param _amount amount of underlying token you want to lend
 */
function lendToken(address _token, uint256 _amount) external traderOrTraderContract nonReentrant {

    require(_token != address(0x0) && _amount > 0, "04");
    require(isLendToken[_token], "02");

    IVenusToken(_token).mint(_amount);

    uint256 tokenPriceInUSD = venusPriceOracle.getUnderlyingPrice(_token);
    uint256 amountInUSD = _amount.mul(tokenPriceInUSD).div(10 ** IBEP20Token(underlying[_token]).decimals());
    totalLendedAmountInUSD = totalLendedAmountInUSD.add(amountInUSD);

    emit TokenLended(_token, underlying[_token], _amount);
}
```
````
