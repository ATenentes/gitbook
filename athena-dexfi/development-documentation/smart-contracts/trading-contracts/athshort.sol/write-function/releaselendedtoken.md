---
description: Release lended token on venus platform
---

# releaseLendedToken

````solidity
```solidity
/**
 
 * @notice restricted function, should be called by trader or trader contract only
 * @param _token address of venus token address
 * @param _amount amount of underlying token you want to release
 * @param _fullRelease bool flag, If you want to release full lended amount pass true else pass false.
 */
function releaseLendedToken(address _token, uint256 _amount, bool _fullRelease) external traderOrTraderContract nonReentrant {
    require(_token != address(0x0) && (_fullRelease || _amount > 0), "04");
    require(isLendToken[_token], "02");

    uint256 perTranscBal = IBEP20Token(underlying[_token]).balanceOf(address(this));
    if (_fullRelease) {
        IVenusToken(_token).redeem(IBEP20Token(_token).balanceOf(address(this)));
    } else {
        IVenusToken(_token).redeemUnderlying(_amount);
    }
    uint256 postTranscBal = IBEP20Token(underlying[_token]).balanceOf(address(this));
    uint256 releaseLendedamount = postTranscBal.sub(perTranscBal);
    require(releaseLendedamount != 0, "33");

    uint256 tokenPriceInUSD = venusPriceOracle.getUnderlyingPrice(_token);
    uint256 amountInUSD = releaseLendedamount.mul(tokenPriceInUSD).div(10 ** IBEP20Token(underlying[_token]).decimals());

    if (totalLendedAmountInUSD > amountInUSD) {
        totalLendedAmountInUSD = totalLendedAmountInUSD.sub(amountInUSD);
    } else {
        totalLendedAmountInUSD = 0;
    }

    // claim pending XVS token
    claimXVSToken();

    emit LendedTokenReleased(_token, underlying[_token], releaseLendedamount);
}
```
````
