# AthShort

## - constructor

```
@param _startTime {uint256} : unix start timestamp of short order contract
@param _traderContractAddress {address} : address of AthTrader contract
@param _traderAddress {address} : address of trader account
@param _participationTokenAddress {address} : address of participation(ERC-20)Token
@param _borrowLimitInPer {uint256} : borrow limit in percentage in 2 decimal precision
```



## - setStartTime

```
@notice : set the start time of trading
```

## - internalTraderOrTraderContract

```
@notice : check if the caller is trader or trader contract
```

## - setShortFactory

```
@notice : set shortFactory address
@param _shortFactory {address} : address of shortFactory
```

## - lendToken

```
@notice : lend token Venus Platform
@param _token {address} : address of venus token address
@param _amount {uint256} : amount of underlying token you want to lend
```

## - releaseLendedToken

```
@notice : release lended token on venus platform
@param _token {address} : address of venus token address
@param _amount {uint256} : amount of underlying token you want to release
@param _fullRelease {bool} : if you want to release full lended amount pass true, else pass false
```

## - borrowToken

```
@notice : borrow token from venus platform
@param _token {address} : address of venus token address
@param _amount {uint256} : amount of underlying token you want to borrow
```

## - repayBorrowToken

```
@notice : repay borrowed token from venus platform
@param _token {address} : address of venus token address
@param _amount {uint256} : amount of underlying token you want to repay
@param _fullRelease {bool} : if you want to repay full borrowed amount pass true, else pass false
```

## - claimXVSToken

```
@notice : claim XVS rewarded due to borrow/lend on venus platform
```

## - transferTokenToTraderContract

```
@notice : transfer token from short order contract to trader contract
@param _token {address} : address of ERC20 token address
@param _amount {uint256} : amount of ERC20 token need to be transfered
```

## - whitelistLendToken

```
@notice : add to whitelist allowed token to borrowed from venus
@param _token {address[]} : array of venus token address which is allowed to be borrowed on venus
```

## - delistLendToken

```
@notice : remove from whitelist, allowed token to lend on venus
@param _token {address} : venus token address which is not allowed to be lended on venus
```

## - whitelistBorrowToken

```
@notice : add to whitelist allowed token to borrowed from venus
@param _token {address[]} : array of venus token address which is allowed to be borrowed on venus
```

## - delistBorrowToken

```
@notice : remove from whitelist, allowed token to borrow from venus
@param _token {address} : venus token address which is not allowed to be borrowed from venus
```

## - updateBorrowLimit

```
@notice : update borrow limit in percentage
@param _borrowLimitInPer {uint256} : allowed borrow limit in percentage (50% means 5000)
```

## - updateTraderAddress

```
@notice : update trader address
@param _addr {address} : address of trader account
```

## - updateTraderContractAddress

```
@notice : update trader contract address
@param _borrowLimitInPer {address} : address of trader contract
```
