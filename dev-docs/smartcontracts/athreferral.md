---
description: Referral records and commission management Contract
---

# AthReferral

## - onlyOperator

```
@notice : check if caller is operator
```

## - addAdmin

```
@notice : assign Administrator permission
@param user {address} : the address to get Admin permission

onlyOwner
```

## - removeAdmin

```
@notice : remove Administrator permission
@param user {address} : the address to be removed Admin permission

onlyOwner
```

## - isAdmin

```makefile
@notice : check if given address is Administrator
@param user {address} : the address to be checked Admin permission
@returns : the judgement value
```

## - claimableAmountByOperator

```
@notice : get the claimable amount of specific referrer from given operator
@param _referrer {address} : the address which calculates the claimbale amount
@param _operator {address} : the address which includes claimable amount
@returns : claimable amount
```

## - isReferralContract

```
@notice : check current contract is AthReferral contract
@returns : the judgement value
```

## - getReferrer

```
@notice : get Referrer of certain user
@returns : the address of user to get Referrer
```

## - addOperatorToken

```
@notice : set given token address as operator token
@param _token {address} : the address of token to set
```

## - \_recordReferral

```makefile
@notice : record information of referrer and user
@param _user {address} : the address of user who get refer
@param _referrer {address} : the address of referrer who refer user

private
```

## - recordReferral

```makefile
@notice : record referral infromation
@dev : call _recordReferral function
@param _user {address} : the address of user who get refer
```

## - \_addUserReferrer

```makefile
@notice : add infromation of referrer refers user
@param _referrer {address} : the address of referrer who refer user
@param _user {address} : the address of user who get refer

private
```

## - addUserReferrer

```makefile
@notice : add infromation of referrer refers user
@dev : just only call _addUserReferrer function
@param _referrer {address} : the address of referrer who refer user
@param _user {address} : the address of user who get refer

onlyOwner
```

## - \_recordReferralCommission

```makefile
@notice : record info of referrer, user, claimable amount
@returns : the address of referrer who refer user
```

## - recordReferralCommission

```makefile
@notice : record info of referrer, user, claimable amount
@dev : call _recordReferralCommission function
@returns : the address of referrer who refer user
```

## - isOperator

```makefile
@notice : check address is operator
@param _user {address} : the address to be checked
@returns : judgement value
```

## - addOperator

```makefile
@notice : assign operator permission
@param _operator {address} : the address to get operator permission

onlyAdmin
```

## - removeOperator

```makefile
@notice : remove operator permission
@param _operator {address} : the address to be removed operator permission

onlyAdmin
```

## - drainBEP20Token

```makefile
@notice : drain tokens received by mistake
@param _token {IATHERC20} : the erc20 token
@param _amount {uint256} : the token amount to drain
@param _to {address} : the address to be sent tokens

onlyOwner
```

## - claimCommissionByOperator

```makefile
@notice : claim commission from operator to referrer
@param _operator {address} : the operator address who is owner
```

## - getOperatorReferralRecords

```makefile
@notice : get the info of refer detail
@param _operator {address} : the address of owner
@param _referrer {address} : the address to get info
@returns : token address for transfer
@returns : total amount of tokens to transfer 
@returns : information of individual user
```
