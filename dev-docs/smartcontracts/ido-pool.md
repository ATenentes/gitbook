# IDO pool



## - constructor

```
@param _token {address} : address of token for sale
@param _tokenDecimal {uint256} : the decimal number of token
@param _currency {address} : address of curreny used for the IDO pool
@param _startTime {uint256} : the time when presale starts
@param _fundingPeriod {uint256} : funding period in seconds
@param _releaseTime {uint256} : the time token released
@param _price {uint256} : the price of token for IDO pool
@param _totalAmount {uint256} : the total amount for IDO pool
@param _chainId {uint256} : the chainId which token deployed
@param _softCap {uint256} : the minimum amount of IDO pool
@param _hardCap {uint256} : the maximum amount of IDO pool
@param _devTeamAddr {address} : the address of dev team wallet
@param _maxContribute {uint256} : the maximum amount of investing
@param _minContribute {uint256} : the minimum amount of investing
```



## - isParticipationTimeCrossed

```
@notice : determine whether investor can buy depending on the investor type
@param _investoryType {InvestorType} : type of the investor's level
@return : return result
```



## - transferCurrencyToken

```
@notice : transfer collectedFee to owner and transfer remain amount dev team wallet address
```



## - claimableAmount

```
@notice : get the claimable amount of IDO token about given address
@param _user {address} : given address
@return : available amount to claim
```



## - addressToString

```
@notice : convert address to string
@param _address {address} : address to be converted
@return : string of address converted
```



## - getDetailByAddress

```
@notice : get all information of investor
@param _investor {address} : address of investor
@returns : address of investor
@returns : amount of participated
@returns : token amount to claimable
@returns : address for withdrawal
```



## - getInvestorsDetails

```
@notice : get the investors' information of the IDO
@returns : array of investors
@returns : array of invested amount
@returns : array of allocated amount
@returns : array of address for withdrawal
```



## - getInvestorList

```
@notice : get investor address of the IDO
@returns : array of investor addresses
```



## - getTotalReferralFeePaid

```
@notice : get the total referral fee paid amount
@returns : total referral amount
```



## - withdraw

```
@notice : withdraw tokens after the sale ends and burns the remaining tokens
```

## - emergencyWithdraw

```
@notice : withdraw in case of any possible hack/vulnerability
```



## - setTierInfo

```solidity
@notice : match fees and tiers according levels
```



## - setAthStaking

```
@notice : set the AthStaking address
@param _athStaking {address} : address of AthStaking contract
```

## - setAthReferral

```
@notice : set the AthReferral address
@param _referralAddress {address} : address of AthReferral contract
```

## - setDevAddress

```
@notice : set the dev address
@param _devAddr {address} : address of dev team wallet
```

## - setTokenAddress

```
@notice : set the dev address
@param _token {address} : address of token contract
```

## - setFundingPeriod

```
@notice : set funding period
@param _fundingPeriod {uint256} : new funding period
```

## - setEndTime

```
@notice : set the end time
@param _endTime {uint256} : new end time
```

## - setReleaseTime

```
@notice : set the release time
@param _releaseTime {uint256} : new release time
```

## - setReleaseTime

```
@notice : set the release time
@param _releaseTime {uint256} : new release time
```



## - isSoftCap

```
@notice : judge if invest more then softcap
@returns : result of judgement
```



## - poolStatus

```
@notice : get status of IDO pool contract
@returns : status number
```



## - revertCurrency

```
@notice : return currency to the investors
```



## - recoverToken

```
@notice : recover ERC20 token sent to contract by mistake
@param _tokenAddress {address} : ERC20 token address which need to recover 
@param _amount {uint256} : amount of token to be recovered
```



## - supplyIDOToken

```
@notice : supply IDO token to contract
@param _amount {uint256} : amount of token to be supplied
```



## - buy

```
@notice : buy tokens
@param _amount {uint256} : amount of token to buy
@param _claimAddress {address} : address to get claim
```



## - claimTokens

```
@notice : withdraw purchased tokens after release time
```



## - \_calculateReferFee

```
@notice : calculate Referral fee by level and feePaid amount
@param referrer {address} : the address of referrer
@param feePaid {uint256} : amount of fee paid
```



## - bulkToReferral

```
@notice : transfer currency to the referral contract
```
