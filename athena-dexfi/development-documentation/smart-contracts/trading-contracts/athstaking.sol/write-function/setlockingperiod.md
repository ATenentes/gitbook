---
description: Sets locking period
---

# setLockingPeriod

````solidity
```solidity
/**
	 * @dev Sets locking period
	 *
	 * @notice restricted function, should be called by owner only
	 * @param lockingPeriod_ locking period defined in seconds
	 */
    function setLockingPeriod(uint32 lockingPeriod_) external onlyOwner {
        // Emit an event
        emit LockingPeriodChanged(lockingPeriodInSeconds, lockingPeriod_);
        
        // Update locking period
        lockingPeriodInSeconds = lockingPeriod_;
    }
```
````
