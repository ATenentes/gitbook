---
description: IWbnb Interface for deposit & withdraw wrap BNB token.
---

# IWbnb

{% code overflow="wrap" lineNumbers="true" %}
```solidity
interface IWbnb {
    function deposit() external payable;

    function withdraw(uint wad) external;
}
```
{% endcode %}
