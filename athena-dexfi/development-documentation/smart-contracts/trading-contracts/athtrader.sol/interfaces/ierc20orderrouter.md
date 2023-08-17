# IERC20ORDERROUTER

{% code overflow="wrap" lineNumbers="true" %}
```solidity
interface IERC20ORDERROUTER {
    function depositToken(
        uint256 _amount,
        address _module,
        address _inputToken,
        address payable _owner,
        address _witness,
        bytes calldata _data,
        bytes32 _secret
    ) external;

}
```
{% endcode %}
