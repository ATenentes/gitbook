# AthQueue

## - constructor

```
@param athStaking_ {address} : the address of athStaking contract
@param referralAddress_ {address} : the address of referral contract
@param owner_ {address} : owner address of owner of entire project
@param trader_ {address} : the address of trader who create queue contract
@param queueInfo_ {address} : the address of queueInfo contract
```

## - transferOwnership

```
@notice : transfer ownership to given address
@param _newOwner {address} : new owner address
```

## - initializeRound

```
@notice : initializes queue contract parameters
@param participationToken_ {address} : address of participation token contract
@param minContribution_ {uint256} : minimum contribution required to participate in funding round
```

## - addToAllowed

```
@notice : add tokens address to allowed list
@param allowed {address[]} : address list of tokens
```

## - removeFromAllowed

```
@notice : removes token address from allowed list
@param notAllowed_ {address[]} : addresses of tokens to be removed
```

## - setShortOrderContractAddr

```
@notice : set short order contract address
@param _addr {address} : new short order contract address
```

## - setTraderFee

```
@notice : set the trader fee
@param _traderFee {uint8} : new trader fee
```

## - recoverContract

```
@notice : recover value from the contract
```

## - concludeTradingContract

```
@notice : end trading contract and set reward rate
@param forceConclude {bool} : pass true to forceConclude without verifing traded token conversion
@param operator {address} : the address of operator of current trading
@param tradedAmount {uint256} : traded amount as participationtoken which would be coming from trading contract
```

## - invest

```
@notice : invest participation tokens to the contract
@param amount_ {uint256} : number of tokens to invest
```

## - withdraw

```
@notice : withdraw invested tokens
```

## - removeByAddress

```
@notice : remove address from investors array
@param address_ {address} : address to be removed
```

## - distributeRewards

```
@notice : distribute fee to users, trader, referrers called by owner
@returns : fee sent to owner
@returns : fee sent to trader
@returns : fee sent to referral contract
```

## - calculateInvestorReward

```
@notice : calculate all following fees of given investor
@returns : the profitability after trading
@returns : total referral fee paid
@returns : total trader fee
@returns : total owner fee
@returns : reward amount
```

## - harvestReward

```
@notice : harvest rewards after trading period gets over
```

## - calculateFee

```
@notice : get fee from surPlus amount and athLevel
@param surPlus {uint256} : surplus amount of participation tokens
@returns : amount of calculated fee
```

## - startTrading

```
@notice : start trading from queue contract
```

## - getTraderInfo

```
@notice : get list of trading address and amount
@returns : list of trading amount
@returns : list of trading address
```

## - getStandbyInfo

```
@notice : get list of standby address and amount
@returns : list of standby amount
@returns : list of standby address
```

## - getclaimableData

```
@notice : get info of given investor
@param investor {address} : the address to get info
@returns : the profitability after trading
@returns : total referral fee paid
@returns : total trader fee
@returns : total owner fee
@returns : profit amount
@returns : total amount after trading
```

## - isOwner

```
@notice : function to check if the caller is owner
```

## - isTrader

```
@notice : function to check if the caller is trader
```

## - isTraderOrOwner

```
@notice : function to check if the caller is trader or owner
```

## - isTraderContract

```
@notice : function to check if the caller is trading contract
```
