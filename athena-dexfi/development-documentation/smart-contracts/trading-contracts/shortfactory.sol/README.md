---
description: AthenaBank staking contract Version 1.0
---

# ShortFactory.sol

Solidity version and import libraries for ShortFactory.sol.

{% code title="ShortFactory.sol" overflow="wrap" %}
````solidity
```solidity
pragma solidity ^0.8.0;

import "./AthShort.sol";

contract ShortFactory {

    /**
    * @dev create instance of this contract
    * @param traderFactory_ address of traderFactory contract
    */
    constructor(address traderFactory_) {
        owner = msg.sender;
        traderFactory = traderFactory_;

    }
    
    ...
}

```
````
{% endcode %}
