---
description: Link to router contract
---

# IROUTER

{% code overflow="wrap" lineNumbers="true" %}
```solidity
interface IROUTER {
    // Swap tokens
    function swapExactTokensForTokens(
        uint amountIn,
        uint amountOutMin,
        address[] calldata path,
        address to,
        uint deadline
    ) external returns (uint[] memory amounts);
}
```
{% endcode %}
