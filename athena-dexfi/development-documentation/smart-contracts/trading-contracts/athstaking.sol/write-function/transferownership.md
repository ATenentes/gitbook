---
description: Transfer ownership to given address
---

# transferOwnership

```solidity
/**
	 * @dev Transfer ownership to given address
	 *
	 * @notice restricted function, should be called by owner only
	 * @param newOwner_ address of new owner
	 */
function transferOwnership(address newOwner_) external onlyOwner {
    // Update owner address
    owner = newOwner_;

    // Emit an event
    emit OwnershipTransferred(msg.sender, newOwner_);
}
```
