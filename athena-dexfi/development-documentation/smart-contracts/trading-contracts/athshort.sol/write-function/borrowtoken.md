---
description: function to borrow token from venus platform
---

# borrowToken

````solidity
```solidity
/**
 * @notice restricted function, should be called by trader or trader contract only
 * @param _token address of venus token address
 * @param _amount amount of underlying token you want to borrow from venus platform
 */
function borrowToken(address _token, uint256 _amount) external traderOrTraderContract nonReentrant {
    require(_token != address(0x0) && _amount > 0, "04");
    require(isBorrowToken[_token], "02");

    uint256 perTranscBal = IBEP20Token(underlying[_token]).balanceOf(address(this));
    if (_token == vBNBToken) {
        IVenusToken(_token).borrow(_amount);
        IWbnb(wbnb).deposit{value : _amount}();
    } else {
        IVenusToken(_token).borrow(_amount);
    }
    uint256 postTranscBal = IBEP20Token(underlying[_token]).balanceOf(address(this));

    uint256 borrowedAmount = postTranscBal.sub(perTranscBal);
    require(borrowedAmount != 0, "34");

    uint256 tokenPriceInUSD = venusPriceOracle.getUnderlyingPrice(_token);
    borrowedAmountInUSD += _amount.mul(tokenPriceInUSD).div(10 ** IBEP20Token(underlying[_token]).decimals());

    require(borrowedAmountInUSD <= totalLendedAmountInUSD.mul(borrowLimitInPer).div(10000), "35");

    emit TokenBorrowed(_token, underlying[_token], _amount);
}
```
````
