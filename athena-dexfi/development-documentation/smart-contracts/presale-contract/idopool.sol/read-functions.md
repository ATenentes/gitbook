---
description: View functions list.
---

# Read Functions

#### public

```
claimableAmount
```

* ````solidity
  ```solidity
  /**
   * @dev claimable amount of IDO token
   * Returns amount IDO token available to claim
   */
  function claimableAmount(address _user) public view returns (uint256 _tokenAmount){
      Sale memory sale = sales[_user];

      if (block.timestamp < releaseTime || sale.tokenWithdrawnStatus || sale.allocatedAmount == 0) {
          return 0;
      }

      uint256 tAmount = sale.allocatedAmount.mul(totalIDOTokenSupplied).div(totalAmountSold);
      _tokenAmount = tAmount.sub(sale.tokensWithdrawn);
  }
  ```
  ````

```solidity
getInvestorType
```

* ```solidity
  /**
   * @dev To get type of investor depending on amount Ath staked
   */
  function getInvestorType(address _user) public view returns (InvestorType level) {
      level = InvestorType(athStaking.athLevel(_user));
      require(level <= InvestorType.LEVEL_3, "Derived Level is out of Range");
  }
  ```

#### external

```solidity
getInvestorsDetails
```

* ```solidity
  /**
   * @dev To get investor of the IDO
   * Returns array of investor addresses and their invested funds
   */
  function getInvestorsDetails() external view returns (address[] memory, uint256[] memory, uint256[] memory) {
      address[] memory addrs = new address[](numberParticipants);
      uint256[] memory funds = new uint256[](numberParticipants);
      uint256[] memory allocatedfunds = new uint256[](numberParticipants);

      for (uint256 i = 0; i < numberParticipants; i++) {
          addrs[i] = sales[investorList[i]].investor;
          funds[i] = sales[investorList[i]].amount;
          allocatedfunds[i] = sales[investorList[i]].allocatedAmount;
      }

      return (addrs, funds, allocatedfunds);
  }
  ```

```solidity
getInvestorList
```

* ```solidity
  /**
       * @dev To get investor address of the IDO
       * Returns only array of investor addresses
       */
      function getInvestorList() external view returns(address[] memory) {
          return investorList;
      }
  ```
