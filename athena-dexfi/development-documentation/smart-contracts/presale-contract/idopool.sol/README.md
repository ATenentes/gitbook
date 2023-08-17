---
description: AthenaBank staking contract Version 1.0
---

# IDOPool.sol

Solidity version and import libraries for IDOPool.sol.

{% code title="IDOPool.sol" overflow="wrap" %}
````solidity
```solidity
pragma solidity 0.6.12;

import "./SafeERC20.sol";
import "./IERC20.sol";
import "./SafeMath.sol";
import "./Ownable.sol";
import "./ReentrancyGuard.sol";

/**
 * @dev Initialzes the TierIDO Pool contract
 * @param _token The ERC20 token contract address
 * @param _tokenDecimal The ERC20 token decimal
 * @param _currency The curreny used for the IDO
 * @param _startTime Timestamp of when pre-Sale starts
 * @param _fundingPeriod funding Period in seconds
 * @param _releaseTime Timestamp of when the token will be released
 * @param _price Price of the token for the IDO
 * @param _totalAmount The total amount for the IDO
 */
//solhint-disable-next-line function-max-lines
constructor(
    address _token,
    uint256 _tokenDecimal,
    address _currency,
    uint256 _startTime,
    uint256 _fundingPeriod,
    uint256 _releaseTime,
    uint256 _price,
    uint256 _totalAmount
) public {
    require(_tokenDecimal > 0, "_tokenDecimal must be greater Zero");
    require(_currency != address(0), "Currency address cannot be address zero");
    require(_startTime >= block.timestamp, "start time > current time");
    require(_fundingPeriod >= 1 hours, "_fundingPeriod time > 1 hour");
    require(_releaseTime > _startTime + _fundingPeriod, "release time > end time");
    require(_totalAmount > 0, "Total amount must be > 0");

    token = IERC20(_token);
    tokenDecimal = _tokenDecimal;
    currency = IERC20(_currency);
    startTime = _startTime;
    endTime = _startTime + _fundingPeriod;
    fundingPeriod = _fundingPeriod;
    releaseTime = _releaseTime;
    price = _price;
    totalAmount = _totalAmount;
    availableTokens = _totalAmount;

    athStaking = IAthStaking(0x48E5Fc0cD874fB2eC9C5dd67d3e141C0DA152DA3);
}

...
}
```
````
{% endcode %}
