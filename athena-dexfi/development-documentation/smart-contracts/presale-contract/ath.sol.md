---
description: ATH FT
---

# ATH.sol

Solidity version and import libraries for ATH.sol.

{% code title="ATH.sol" overflow="wrap" %}
````solidity
```solidity
contract ATHToken is ERC20Burnable, Ownable {
    using SafeMath for uint256;

    uint256 private constant initialSupply = 100e6 * 10**18; //100 million

    constructor(address _user) ERC20("Athena", "ATH") {
        _mint(_user, initialSupply);
    }

    receive() external payable {
        payable(owner()).transfer(msg.value);
    }

    function fallabck() public payable {
        payable(owner()).transfer(getBalance());
    }

    function getBalance() public view returns (uint256) {
        return address(this).balance;
    }
}
```
````
{% endcode %}
