---
description: List of events which is used by ATHShort smart contract.
---

# Events

```
TokenLended Event
```

* ````solidity
  ```solidity
  /**
   * @dev Fired in lendToken()
   *
   * @param token address of an venus Token
   * @param underlyingToken address of underlying Token
   * @param amount amount of underlying token
  */
  event TokenLended(address indexed token, address indexed underlyingToken, uint256 amount);
  ```
  ````

```
LendedTokenReleased
```

* ````solidity
  ```solidity
  /**
  * @dev Fired in releaseLendedToken()
  *
  * @param token address of an venus Token
  * @param underlyingToken address of underlying Token
  * @param amount amount of underlying token
  */
  event LendedTokenReleased(address indexed token, address indexed underlyingToken, uint256 amount);
  ```
  ````

```
TokenBorrowed
```

* ````solidity
  ```solidity
  /**
  * @dev Fired in borrowToken()
  *
  * @param token address of an venus Token
  * @param underlyingToken address of underlying Token
  * @param amount amount of underlying token
  */
  event TokenBorrowed(address indexed token, address indexed underlyingToken, uint256 amount);
  ```
  ````

```
BorrowTokenRepaid
```

* ````solidity
  ```solidity
  /**
   * @dev Fired in repayBorrowToken()
   *
   * @param token address of an venus Token
   * @param underlyingToken address of underlying Token
   * @param amount amount of underlying token
   */
  event BorrowTokenRepaid(address indexed token, address indexed underlyingToken, uint256 amount);
  ```
  ````

```
WhiteListToken
```

* ````solidity
  ```solidity
  /**
  * @dev Fired in whitelistLendToken() and whitelistBorrowToken()
  *
  * @param token address of an venus Token
  * @param underlyingToken address of underlying Token
  */
  event WhiteListToken(address indexed token, address indexed underlyingToken);
  ```
  ````

```
DeListToken
```

* ````solidity
  ```solidity
  /**
  * @dev Fired in delistLendToken() and delistBorrowToken()
  *
  * @param token address of an venus Token
  * @param underlyingToken address of underlying Token
  */
  event DeListToken(address indexed token, address indexed underlyingToken);
  ```
  ````

