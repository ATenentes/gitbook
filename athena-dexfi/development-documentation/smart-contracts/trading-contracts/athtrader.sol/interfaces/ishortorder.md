---
description: Link to short Order Contract
---

# IShortOrder

{% code overflow="wrap" lineNumbers="true" %}
```solidity
interface IShortOrder {
function lendToken(address _token, uint256 _amount) external;

function releaseLendedToken(address _token, uint256 _amount, bool _fullRelease) external;

function borrowToken(address _token, uint256 _amount) external;

function repayBorrowToken(address _token, uint256 _amount, bool _fullRepay) external;

function transferTokenToTraderContract(address _token, uint256 _amount) external;

function underlying(address _token) external view returns (address);
}
```
{% endcode %}
