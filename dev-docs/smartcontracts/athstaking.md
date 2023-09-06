# AthStaking

## - constructor

```makefile
@param _ath {address} : the address of ATHToken
@param _treasury {address} : the address of treasury account
@param _levels {uint8} : athLevel range
@param _depositFee {uint8} : depositFee
@param _lockingPeriodInSeconds {uint32} : defined in terms of seconds
@param _levelBounds {uint256[] memory} : minimum ATHToken required for each level
```

## - excludeFromFee

```
@notice : set address status of excluding from fee
@param _addr {address} : the address which will be set status
@param status {bool} : the new status of address for excluding from fee

onlyOwner
```

## - authorizeStaker

```
@notice : set address staking possiblity
@param _addr {address} : the address which will be set possiblity
@param status {bool} : the new status of address for staking possiblity

onlyOwner
```

## - authorizeLevelmanager

```
@notice : set level manager address
@param _addr {address} : the address which will be set
@param status {bool} : the new status of address for managing level

onlyOwner
```

## - athLevel

```
@notice : Returns ATH level of given address
@param _user {address} : the address of staker
```

## - showExcludeFeeAddress

```
@notice : show the list of excluded Address from fee
@returns : the address list of excluded from fee
```

## - showAuthorizedStakers

```
@notice : show the list of authorized stakers
@returns : the address list of authorized
```

## - showLevelManagers

```
@notice : show the list of authorized level manager
@returns : the address list of authorized level manager
```

## - setAthLevel

```
@notice : set ath level by level manager
@param _address {address} : the address which level will be set
@param _level {uint8} :  the new level

onlyLevelManager
```

## - transferOwnership

```
@notice : transfer ownership to given address
@param _newOwner {address} : new owner address

onlyOwner
```

## - setDepositFee

```
@notice : set new deposit fee
@param _fee {uint8} : new deposite fee

onlyOwner
```

## - setLockingPeriod

```
@notice : set locking period
@param _lockingPeriod {uint32} : new locking period in seconds

onlyOwner
```

## - deposit

```
@notice : deposits ATH tokens to the contract
@param _amount {uint256} : number of ATH tokens to be deposited
@param _level {uint8} : index of level for which amount is deposited
```

## - depositFor

```
@notice : Authorized staker deposit ath token for specific user
@param depositAddr : the address will be deposited by authorized
@param _amount {uint256} : number of ATH tokens to be deposited
@param _level {uint8} : index of level for which amount is deposited

onlyAuthrizedStaker
```

## - withdraw

```
@notice : authorized staker deposit ath token for specific user
@param depositAddr {address} : the address which will be deposited by authorized
@param _amount {uint256} : number of ATH tokens to be deposited
@param _level {uint8} : index of level for which amount is deposited
```
