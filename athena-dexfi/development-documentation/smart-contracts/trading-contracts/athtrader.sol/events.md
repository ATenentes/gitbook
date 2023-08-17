---
description: List of events which is used by ATHTrader smart contract.
---

# Events

```
OwnershipTransferred
```

* ````solidity
  ```solidity
  /**
  	 * @dev Fired in transferOwnership() when ownership is transferred
  	 *
  	 * @param previousOwner an address of previous owner
  	 * @param newOwner an address of new owner
  	 */
      event OwnershipTransferred(address indexed previousOwner, address indexed newOwner);
  ```
  ````

```
Allowed
```

* ````solidity
  ```solidity
  /**
  	 * @dev Fired in addToAllowed() and removeFromAllowed() when address is added into/removed from
       *      allowedTokens
  	 *
  	 * @param token  address
  	 * @param isAllowed defines if address is added or removed
  	 */
      event Allowed(address token, bool isAllowed);
  ```
  ````

```
Recover
```

* ````solidity
  ```solidity
  /**
  	 * @dev Fired in recoverToken() when tokens are recovered by an owner
  	 *
  	 * @param token address of token to recover
  	 */
      event Recover(address token);
  ```
  ````

```
RecoverValue
```

* ````solidity
  ```solidity
  /**
  	 * @dev Fired in recoverContract() when contract value is recovered by an owner
  	 *
  	 * @param amount value of the contract recovered
  	 */
      event RecoverValue(uint256 amount);
  ```
  ````

```
Investment
```

* ````solidity
  ```solidity
  /**
  	 * @dev Fired in invest() when tokens are invested by user
  	 *
  	 * @param investor address of investor
  	 * @param amount number of tokens invested
  	 */
      event Investment(address indexed investor, uint256 amount);
  ```
  ````

```
WithdrawInvestment
```

* ````solidity
  ```solidity
  /**
  	 * @dev Fired in withdraw() and emergencyWithdraw() when tokens are withdrawn by user
  	 *
  	 * @param investor address of an investor
  	 * @param amount number of tokens withdrawn
       * @param isEmergencyWithdrawl true if fired in emergencyWithdraw()
  	 */
      event WithdrawInvestment(address indexed investor, uint256 amount, bool isEmergencyWithdrawl);
  ```
  ````

```
Swap
```

* ```solidity
  /**
   * @dev Fired in swap() when tokens are swapped by a trader or binanceAPI
   *
   * @param executor address of an executor
   * @param router address of router
       * @param path  of tokens to swap
       * @param amountIn amount of input tokens to send
       * @param amountOutMin minimum amount of output tokens that must be received
       * @param deadline unix timestamp after which the transaction will revert
   */
      event Swap(address indexed executor, address router, address[] path, uint amountIn, uint amountOutMin, uint deadline);
  ```

```solidity
Harvest
```

* ```solidity
  /**
   * @dev Fired in harvestReward() tokens are harvested by user
   *
   * @param investor address of an investor
   * @param amount number of tokens harvested
       * @param fee number of tokens paid as fee
   */
      event Harvest(address indexed investor, uint256 amount, uint256 fee);
  ```

```solidity
ReferralPaid
```

* ```solidity
  /**
   * @dev Fired in harvestReward() tokens are transferred to referrer
   *
   * @param referee address of an investor
   * @param amount number of tokens transferred
       * @param referrer number of tokens paid as fee
   */
      event ReferralPaid(address indexed referee, uint256 amount, address indexed referrer);
  ```



