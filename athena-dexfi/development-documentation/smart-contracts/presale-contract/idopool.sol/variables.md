---
description: List of Variables which is used by IDOPool smart contract.
---

# Variables

#### Struct

* ```solidity
  struct Sale {
          address investor; //Address of user/investor
          uint256 amount; //Amount of tokens to be purchased
          uint256 feePaid; //Amount of Tokens Withdrawal
          uint256 allocatedAmount; //Tokens Withdrawal status
      }
  ```

Single Type Variables

* ```solidity
  // DEV TEAM Address
      address public devAddress;
  ```
* ````solidity
  ```solidity
  // List investors
      address[] private investorList;
  ```
  ````
*
