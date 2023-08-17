---
description: Withdraws ATH tokens from the contract
---

# withDraw



````solidity
```solidity
/**
	 * @dev Withdraws ATH tokens from the contract
	 *
	 * @notice withdrwal can be done after locking period gets over
	 */
function withDraw() external {
    require(
        block.timestamp - athBalance[msg.sender].lastUpdated > lockingPeriodInSeconds,
        "51"
    );

    // Transfer locked ATH amount to staker
    IBEP20Token(athToken).transfer(msg.sender, athBalance[msg.sender].lockedAmount);

    // Emit an event
    emit Unstake(msg.sender, athBalance[msg.sender].lockedAmount);

    // Remove staking data for given address
    delete athBalance[msg.sender];
}
```
````
