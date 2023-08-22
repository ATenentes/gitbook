# AthenaLaunchPadInfo

## - addPresaleAddress

```
@notice : add presale addresses to the list
@param _presale {address} : address of presale contract
@param _presaleProjectID {uint256} : the number of presale contract
```



## - getPresaleCount

```
@notice : return the count of presale contracts
@return : the count of presale contracts
```



## - getPresaleAddressByDbId

```
@notice : get the presale contract address of given DB id
@param asvaDbId {uint256} : the number of id
@return :  the address of presale contract
```

## - getPresaleAddress

```
@notice : get the presale contract address of given asvaid
@param asvaId {uint256} : the number of asvaid
@return :  the address of presale contract
```

## - validAsvaId

```
@notice : check it the asvaId is valid
@param asvaId {uint256} : the number of asvaid
@return :  result of validator
```

## - addOperator

```
@notice : assign operator Role
@param _addr {uint256} : address to be added
@return :  result of contract
```

## - removeOperator

```
@notice : assign operator Role
@param _addr {uint256} : address to be removed
@return :  result of contract
```
