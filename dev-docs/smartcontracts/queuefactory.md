# QueueFactory

## - constructor

```
@param athStaking_ {address} : address of athStaking contract
@param referralAddress_ {address} : address of referral contract
@param queueInfo_ {address} : address of queue info contract
```

## - setAthStaking

```
@notice : set the address of athStaking contract
@param athStaking_ {adderess} : address of athStaking contract
```

## - setReferralContract

```
@notice : set the address of referral contract
@param referralAddress_ {address} : address of referral contract
```

## - isOwner

```
@notice : check if the caller is owner
```

## - transferOwnership

```
@notice : set new owner of this contract
@param newOwner_ {address} : address of new owner
```

## - setTraderDeploymentFee

```
@notice : set the fee that  trader needs to pay for deploying a tradingContract
@param fee_ {address} : fee that trader needs to pay for deploying a tradingContract
```

## - createQueue

```
@notice : deploy a queue contract
@dev : call _deployQueue function
@param traderEOA_ {address} : address of trader
```

## - createQueueByOwner

```
@notice : deploy a queue contract without fee by owner
@dev : call _deployQueue function
@param traderEOA_ {address} : address of trader
```

## - \_deployQueue

```
@notice : deploy a trading contract
@param traderEOA_ {address} : address of trader
```
