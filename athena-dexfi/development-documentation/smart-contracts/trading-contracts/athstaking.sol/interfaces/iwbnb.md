---
description: IWbnb Interface for deposit & withdraw wrap BNB token.
---

# IWbnb

{% code overflow="wrap" lineNumbers="true" %}
```solidity
interface IBEP20Token {
  function transferFrom(
    address _from,
    address _to,
    uint256 _value
  ) external returns (bool success);
  
  function transfer(
    address _to,
    uint256 _value
  ) external returns (bool success);

}
```
{% endcode %}
