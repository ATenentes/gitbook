---
description: AthenaBank staking contract Version 1.0
---

# AthenaPoolFactory.sol

Solidity version and import libraries for AthenaPoolFactory.sol.

{% code title="AthenaPoolFactory.sol" overflow="wrap" %}
````solidity
```solidity
pragma solidity 0.6.12;
pragma experimental ABIEncoderV2;

import "./SafeERC20.sol";
import "./IERC20.sol";
import "./SafeMath.sol";
import "./Ownable.sol";
import "./IDOPool.sol";
import "./AthenaLaunchPadInfo.sol";

    /**
     * @dev Sets the values for {_athenaPadInfoAddress, _athStaking, _devAddress}
     */
    constructor(address _athenaPadInfoAddress, address _athStaking, address _devAddress) public {
        athenaPadInfo = AthenaLaunchPadInfo(_athenaPadInfoAddress);
        athStaking = _athStaking;
        devAddress = _devAddress;
    }

    ...
}
```
````
{% endcode %}
