---
description: List of events which is used by ATHStaking smart contract.
---

# Events

```
OwnershipTransferred
```

* ```solidity
  /**
   * @dev Fired in transferOwnership() when ownership is transferred
   *
   * @param previousOwner an address of previous owner
   * @param newOwner an address of new owner
   */
      event OwnershipTransferred(address indexed previousOwner, address indexed newOwner);
  ```

```
FeeChanged
```

* ```solidity
  /**
   * @dev Fired in setDepositFee() when fee is revised by an owner
   *
   * @param previousFee previous fee in terms of percentage
   * @param newFee new fee in terms of percentage
   */
      event FeeChanged(uint8 previousFee, uint8 newFee);
  ```

```
LockingPeriodChanged
```

* ```solidity
    /**
   * @dev Fired in setLockingPeriod() when locking period is revised by an owner
   *
   * @param previousPeriod previous period defined in seconds
   * @param newPeriod new period defined in seconds
   */
      event LockingPeriodChanged(uint32 previousPeriod, uint32 newPeriod);
  ```

```
Stake
```

* ```solidity
  /**
   * @dev Fired in deposit() when ATH token staked by an address
   *
   * @param staker address of staker
   * @param amount amount of ATH token staked
       * @param fee deposit fee paid to treasury
       * @param level assigned ATH level based on staking amount
   */
      event Stake(address indexed staker, uint256 amount, uint256 fee, uint8 level);
  ```

```
Unstake
```

* ```solidity
  /**
   * @dev Fired in withdraw() when ATH token unstaked by an address
   *
   * @param staker address of staker
   * @param amount amount of ATH token unstaked
   */
      event Unstake(address indexed staker, uint256 amount);
  ```

