---
description: Deposits ATH tokens to the contract
---

# deposit

````solidity
```solidity
/**
	 * @dev Deposits ATH tokens to the contract
	 *
	 * @param amount_ number of ATH tokens to be deposited
	 * @param level_ index of level for which amount is deposited
	 */
function deposit(uint256 amount_, uint8 level_) external {
    require(level_ > 0 && level_ <= levels, "49");

    require(
        amount_ + athBalance[msg.sender].balance == minAthRequired[level_] && amount_ > 0,
        "15"
    );

    // Check if locking period is running
    if(athBalance[msg.sender].lastUpdated != 0) {
        require(
            block.timestamp - athBalance[msg.sender].lastUpdated <= lockingPeriodInSeconds,
            "50"
        );
    }

    // Calculate deposit fee
    uint256 _fee = (amount_ * depositFee) / 100;

    // Transfer locking amount to AthStaking contract
    IBEP20Token(athToken).transferFrom(msg.sender, address(this), amount_ - _fee);

    // Check if fee is non zero
    if(_fee > 0) {
        // Transfer fee to treasury account
        IBEP20Token(athToken).transferFrom(msg.sender, treasury, _fee);
    }

    // Increment ATH balance by given amount
    athBalance[msg.sender].balance += amount_;

    // Increment ATH locking amount
    athBalance[msg.sender].lockedAmount += (amount_ - _fee);

    // Record deposit time
    athBalance[msg.sender].lastUpdated = uint32(block.timestamp);

    // Record index of ATH level
    athBalance[msg.sender].level = level_;

    // Emit an event
    emit Stake(msg.sender, amount_, _fee, level_);
}
```
````
