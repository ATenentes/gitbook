---
description: function to repay borrowed token from venus platform
---

# repayBorrowToken

````solidity
```solidity
/**
 * @notice restricted function, should be called by trader or trader contract only
 * @param _token address of venus token address
 * @param _amount amount of underlying token you want to repay to venus platform
 * @param _fullRepay bool flag, If you want to repay full borrowed amount pass true else pass false.
 */
function repayBorrowToken(address _token, uint256 _amount, bool _fullRepay) external traderOrTraderContract nonReentrant {
    require(_token != address(0x0) && (_fullRepay || _amount > 0), "04");
    require(isBorrowToken[_token], "02");

    uint256 perTranscBal = IBEP20Token(underlying[_token]).balanceOf(address(this));
    if (_token == vBNBToken) {
        if (_fullRepay) {
            _amount = IVenusToken(_token).borrowBalanceCurrent(address(this));
        }
        IWbnb(wbnb).withdraw(_amount);
        IVenusToken(_token).repayBorrow{value : _amount}();
    } else {
        if (_fullRepay) {
            IVenusToken(_token).repayBorrow(MAX_INT);
        } else {
            IVenusToken(_token).repayBorrow(_amount);
        }
    }
    uint256 postTranscBal = IBEP20Token(underlying[_token]).balanceOf(address(this));

    uint256 repayAmount = perTranscBal.sub(postTranscBal);
    require(repayAmount != 0, "36");

    uint256 tokenPriceInUSD = venusPriceOracle.getUnderlyingPrice(_token);
    uint256 repayAmountInUSD = repayAmount.mul(tokenPriceInUSD).div(10 ** IBEP20Token(underlying[_token]).decimals());

    if (borrowedAmountInUSD > repayAmountInUSD) {
        borrowedAmountInUSD = borrowedAmountInUSD.sub(repayAmountInUSD);
    } else {
        borrowedAmountInUSD = 0;
    }

    emit BorrowTokenRepaid(_token, underlying[_token], repayAmount);
}
```
````
