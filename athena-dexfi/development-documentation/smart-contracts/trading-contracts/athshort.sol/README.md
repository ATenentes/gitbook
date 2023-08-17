---
description: AthenaBank Short Order contract Version 1.0.
---

# ATHShort.sol

Solidity version and import libraries for ATHShort.sol which is inherited by Ownable, ReentrancyGuard abstarct contracts.

{% code title="ATHShort.sol" overflow="wrap" %}
````solidity
pragma solidity ^0.8.0;

import "@openzeppelin/contracts/utils/math/SafeMath.sol";
import "./interfaces/IBEP20Token.sol";
import "./interfaces/ISHORTFACTORY.sol";

```solidity
contract AthShort is Ownable, ReentrancyGuard {
    using SafeMath for uint256;
    
    ...
    
    constructor(uint256 _startTime,
        address _traderContractAddress,
        address _traderAddress,
        address _participationTokenAddress,
        uint256 _borrowLimitInPer) {

        START_TIME = _startTime;
        traderContract = _traderContractAddress;
        trader = _traderAddress;
        participationToken = _participationTokenAddress;
        borrowLimitInPer = _borrowLimitInPer;
        venusComptroller = IVenusComptroller(0xfD36E2c2a6789Db23113685031d7F16329158384);
        venusPriceOracle = IVenusPriceOracle(0xd8B6dA2bfEC71D684D3E2a2FC9492dDad5C3787F);
        vBNBToken = address(0xA07c5b74C9B40447a954e1466938b865b6BBea36);
        wbnb = address(0xbb4CdB9CBd36B01bD1cBaEBF2De08d9173bc095c);

        // vbnb: 0xA07c5b74C9B40447a954e1466938b865b6BBea36
        // vETH: 0xf508fCD89b8bd15579dc79A6827cB4686A3592c8
        // vBTC: 0x882C173bC7Ff3b7786CA16dfeD3DFFfb9Ee7847B
    }
    
    ...
}
```
````
{% endcode %}
