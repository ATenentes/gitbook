---
description: List of Variables which is used by ATHShort smart contract.
---

# Variables

#### Struct

* ```solidity
  struct IDOPoolInfo {
      address contractAddr; //The contract address
      address currency; //The curreny used for the IDO
      address token; //The ERC20 token contract address
      uint256 tokenDecimal;
  }
  ```
* ```solidity
  struct IDOInfo {
      address _token;     //The ERC20 token contract address
      uint256 _tokenDecimal;      //The ERC20 token decimal
      address _currency;      //The curreny used for the IDO
      uint256 _startTime;     //Timestamp of when pre-Sale starts
      uint256 _fundingPeriod;     //Timestamp of when the token will be released
      uint256 _releaseTime;       //Price of the token for the IDO
      uint256 _price;     //The total amount for the IDO
      uint256 _totalAmount;       //The PreSale project ID
      uint256 _presaleProjectID;      //An array of participation fee as per tiers
      uint256[] _participationFees;       //An array of max investments amount in tiers
      uint256[] _maxAmountThatCanBeInvestedInTiers;       //An array of amounts as per tiers
  }
  ```

Single Type Variables

* ```solidity
  address public athStaking; // Ath Staking contract
  ```
* ```solidity
  address public devAddress; // DEV TEAM Address
  ```
