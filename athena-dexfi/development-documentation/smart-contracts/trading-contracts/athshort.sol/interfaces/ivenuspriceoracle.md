---
description: IVenusPriceOracle Interface to define utility functions for VenusPriceOracle .
---

# IVenusPriceOracle

{% code overflow="wrap" lineNumbers="true" %}
````solidity
```solidity
interface IVenusPriceOracle {
    function getUnderlyingPrice(address vToken) external view returns (uint);
}
```
````
{% endcode %}
