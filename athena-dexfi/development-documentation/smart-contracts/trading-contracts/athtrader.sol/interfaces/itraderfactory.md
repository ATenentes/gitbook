---
description: Wrappers over Solidity's arithmetic operations
---

# ITRADERFACTORY

{% code overflow="wrap" lineNumbers="true" %}
```solidity
interface ITRADERFACTORY {

function AllowedTokens(address) external view returns (bool);

function athLevelFee(uint8) external view returns (uint8);

function referrerFeeFromLevel(uint8) external view returns (uint8);

function traderFee() external view returns (uint8);

}
```
{% endcode %}
