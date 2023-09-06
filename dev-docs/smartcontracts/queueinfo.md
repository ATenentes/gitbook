---
description: >-
  Contain all queue information and set basic parameters to generate Queue
  Factory
---

# QueueInfo

## - isOwner

```
@notice : check if the msg.sender is owner
```

## - isAdmin

```
@notice : check if the msg.sender is administrator
```

## - setAdmin

```
@notice : set the administrator address,  only called by Admin or owner
@param _admin {address} : the new admin address
```

## - transferOwnership

```
@notice : set owner of this contract, only owner can call this function
@param newOwner_ {address} : address of new owner
```

## - setShortFactory

```
@notice : set the address of shortFactory, only owner can call this function
@param shortFactory_ {address} : address of shortFactory_ contract
```

## - queuesLength

```
@notice : get the number of queues
```

## - getQueues

```
@notice : get the list of queues
```

## - addQueues

```
@notice : add queue address into queues, only admin call this function
@param queueAddr {address} : address of new queue
```

## - removeQueuesByAddress

```
@notice : removes queues of given address from queues array, only owner call this function
@param queuesToRemove_ {address[]} : array of queues addresses to be removed
```

## - removeQueueByIndex

```
@notice : removes queues of given index from queues array, only owner call this function
@param index_ {uint256} : index of queue to be removed
```

## - addShortToQueue

```
@notice : deploy and associate a short contract with a trading contract, only owner call this function
@param queueContract_ {address} : address of queue Contract to be associated with
```

## - addTraders

```
@notice : add trader in the queue info, only admin can call this function
@param _trader {address} : the address of trader to be added
```

## - isTraderCreated

```
@notice : check if the trader is added
@param _trader {address} : the address of _trader
@returns : judgement value
```

## - setTraderFee

```
@notice : set the fee that goes to trader in %, only owner call this function
@param fee_ {uint8} : fee that goes to trader in %
```

## - setAthLevelFee

```
@notice : set the fee that investor pays on profits in % for given level, only owner call this function
@param level_ {uint8[]} : array of levels
@param fee_ {uint8[]} : array of fees in % respective to levels
```

## - setReferrerFeeFromLevel

```
@notice : set the fee that referrer gets  in % for given level, only owner
@param level_ {uint8[]} : array of levels
@param fee_ {uint8[]} : array of fees in % respective to levels
```

## - addAllowedToken

```
@notice : add tokens to the list of allowed tokens for trading, only owner
@param tokens_ {address[]} : array of tokens to be added
```

## - removeAllowedToken

```
@notice : remove tokens from the list of allowed tokens for trading, only owner
@param tokens_ {address[]} : array of tokens to be removed
```
