# ShortFactory



## - constructor

```
@param queueFactory_ {address} : address of queueFactory contract
```

## - setQueueFactory

```
@notice : set the address of queueFactory
@param queueFactory_ {address} : address of queueFactory contract
```

## - setBorrowLimitInPer

```
@notice : set the borrow limit in percentage
@param borrowLimitInPer_ {uint256} : borrow limit in percentage
```

## - addAllowedLendToken

```
@notice : add tokens to the list of allowed tokens for lending
@param tokens_ {address[]} : array of tokens to be added
```

## - removeAllowedLendToken

```
@notice : remove tokens from the list of allowed tokens for lending
@param tokens_ {address[]} : array of tokens to be removed
```

## - addAllowedBorrowToken

```
@notice : add tokens to the list of allowed tokens for borrowing
@param tokens_ {address[]} : array of tokens to be added
```

## - removeAllowedBorrowToken

```
@notice : remove tokens from the list of allowed tokens for borrowing
@param tokens_ {address[]} : array of tokens to be removed
```

## - setOwner

```
@notice : set owner address
@param owner_ {address} : address of owner
```

## - shortsLength

```
@notice : get length of shorts array
```

## - removeShortByIndex

```
@notice : remove short contract from shorts array by index
@param index_ {uint256} : index of short contract to be removed
```

## - removeShortByAddress

```
@notice : removes short contract from shorts array by address
@param shorts_ {address[]} : array of addresses of short contracts to be removed
```

## - createShort

```
@notice : create short contract
@param _startTime {uint256} : start time of short contract
@param _queueContractAddress {address} : address of queue contract
@param _queueAddress {address} : address of queue
@param _participationTokenAddress {address} : address of token to be used for participation
@returns : address of AthShort newly created
```
