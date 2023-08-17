---
description: AthenaBank staking contract Version 1.0
---

# AthStaking.sol

Solidity version and import libraries for AthStaking.sol.

<pre class="language-solidity" data-title="ATHShort.sol" data-overflow="wrap"><code class="lang-solidity">pragma solidity ^0.8.0;

```solidity
contract AthStaking {
    using SafeMath for uint256;
    
    ...

<strong>    constructor(
</strong>        address ath_,
        address treasury_,
        uint8 levels_,
        uint8 depositFee_,
        uint32 lockingPeriodInSeconds_,
        uint256[] memory levelBounds_
    ) {
        require(levelBounds_.length == levels_, "04");

        //---Setup smart contract internal state---//
        owner = msg.sender;
        athToken = ath_;
        treasury = treasury_;
        levels = levels_;
        depositFee = depositFee_;
        lockingPeriodInSeconds = lockingPeriodInSeconds_;

        for(uint8 i = 1; i &#x3C;= levels_; i++) {
            minAthRequired[i] = levelBounds_[i - 1];
        }
    }
    
    ...
}
```
</code></pre>
