# IGELATOCORE

```solidity
interface IGELATOCORE {
    function cancelOrder(
        address _module,
        address _inputToken,
        address payable _owner,
        address _witness,
        bytes calldata _data
    ) external;

    function vaultOfOrder(
        address _module,
        address _inputToken,
        address payable _owner,
        address _witness,
        bytes memory _data
    ) external view returns (address);
}
```
