---
description: Sets new deposit fee
---

# setDepostFee

````solidity
```solidity
/**
	 * @dev Sets new deposit fee
	 *
	 * @notice restricted function, should be called by owner only
	 * @param fee_ deposit fee defined in percentage of deposited amount
	 */
    function setDepostFee(uint8 fee_) external onlyOwner {
        require(fee_ >= 0 && fee_ <=100, "04");

        // Emit an event
        emit FeeChanged(depositFee, fee_);

        // Update deposit fee
        depositFee = fee_;
    }
```
````
