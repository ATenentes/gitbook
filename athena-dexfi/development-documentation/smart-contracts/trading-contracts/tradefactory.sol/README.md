---
description: AthenaBank staking contract Version 1.0
---

# TradeFactory.sol

Solidity version and import libraries for TradeFactory.sol.

{% code title="TradeFactory.sol" overflow="wrap" %}
````solidity
```solidity
pragma solidity ^0.8.0;

import "./AthTrader.sol";
import "./interfaces/ISHORTFACTORY.sol";


contract TraderFactory {

    /**
    * @dev create instance of this contract
    * @param athLevel_ address of AthLevel contract
    * @param shortFactory_ address of shortFactory contract
     */
    constructor(address athLevel_, address shortFactory_) {
        owner = msg.sender;
        athLevel = athLevel_;
        shortFactory = shortFactory_;

    }
    ...
}
```
````
{% endcode %}
