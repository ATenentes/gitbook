---
description: Contain all swapping and lending functions trading contract
---

# AthTrader

## - constructor

```
@param owner_ {address} : address of owner
@param trader_ {address} : address of trader wallet
@param queueFactory_ {address} : address of queueFactory contract
@param participationToken_ {address} : address of participation token
@param queueContract_ {address} : address of queue contract
@param queueInfo_ {address} : address of queueInfo contract
```

## - setShortOrderContractAddr

```
@notice : set short order contract address
@param _addr {address} : short order contract address
OnlyOwner
```

## - getTradedTokenList

```
@notice : get array of trader token
@returns : array of trader tokens
```

## - endTradingContract

```
@notice : conclude trading contract and send all fund to queue contract
onlyTrader
```

## - terminateTradingContract

```
@notice : conclude trading contract in ending by owner time and send all fund to queue contract
```

## - isTradedTokenConverted

```
@notice : check if all traded tokens are converted
@returns : true if all traded token is converted back to participation token
```

## - swap

```
@notice : swaps tokens invested in contract
@param router_ {address} : address of router
@param memory route_ {address[]} : token path to swap
@param amountIn_ {uint} : amount of input tokens to send
@param amountOutMin_ {uint} : minimum amount of output tokens that must be received
@param deadline_ {uint} : unix timestamp after which the transaction will revert

onlyTrader
```

## - depositToken

```
@notice : calls the correct Gelato module to place both limit and stop orders
@param _amount {uint256} : amount of tokens to be swapped
@param _module {address} : module to be used for placing order (limit order or stop order)
@param _inputToken {address} : address of input token
@param _owner {address} : address of order owner - this contract
@param _witness {address} : address of order witness, used by Gelato
@param _data {bytes} : data to be passed to Gelato, contains outputToken
@param _secret {bytes32} : key to generate witness, used by Gelato

onlyTrader
```

## - CancelOrder

```
@notice : calls GelatoCore to cancel a specific order
@param _module {address} : module used for order
@param _inputToken {address} : address of input token
@param _owner {address} : address of order Owner - this contract
@param _witness {address} : address of order witness
@param _data {bytes} : data used for order 

traderOrOwner
```

## - lendToken

```
@notice : lend token Venus Platform
@param _token {address} : address of venus token address
@param _amount {uint256} : amount of underlying token to lend

onlyTrader
```

## - releaseLendedToken

```
@notice : release lended token on venus platform
@param _token {address} : address of venus token address
@param _amount {uint256} : amount of underlying token to release
@param _fullRelease {bool} : if you want to release full lended amount pass true else pass false

onlyTrader
```

## - borrowToken

```
@notice : borrow token from venus platform
@param _token {address} : address of venus token
@param _amount {uint256} : amount of underlying token you want to borrow from venus platform

onlyTrader
```

## - repayBorrowToken

```
@notice : repay borrowed token from venus platform
@param _token {address} : address of venus token
@param _amount {uint256} : amount of underlying token you want to repay to venus platform
@param _fullRepay {bool} : if you want to repay full borrowed amount pass true else pass false

onlyTrader
```

## - transferTokenToSOContract

```
@notice : send ERC20 token to Short-order contract
@param _token {address} : address of ERC20 token address
@param _amount {uint256} : amount of token want to send to Short-order contract

onlyTrader
```

## - RecoverTokenFromSOContract

```
@notice : function to collect/transfer ERC20 token from Short-order contract
@param _token {address} : address of ERC20 token address
@param _amount {uint256} : amount of token want to recover/transfer from Short-order contract

onlyTrader
```

## - internalSwap

```
@notice : swap tokens invested in contract
@param router_ {address} : address of router
@param route_ {address[]} : token path to swap
@param amountIn_ {uint} : amount of input tokens to send
@param amountOutMin_ {uint} : minimum amount of output tokens that must be received
@param deadline_ unix {uint} : timestamp after which the transaction will revert

internal
```

## - recoverToken

```
@notice : recover tokens from the contract
@param token_ {address} : address of token to recover

onlyTrader
```

## - isTrader

```
@notice : check if caller is trader

internal view
```

## - isOwner

```
@notice : check if caller is owner

internal view
```

## - isTraderOrOwner

```
@notice : check if caller is trader or owner

inernal view
```
