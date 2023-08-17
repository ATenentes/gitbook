---
description: List of Variables which is used by ATHShort smart contract.
---

# Variables

Variables

* ```solidity
  // Token for sale
  IERC20 public token;
  ```
* ```solidity
  // Token Decimal
  uint256 public tokenDecimal;
  ```
* ```solidity
  // Token used to buy
  IERC20 public currency;
  ```
* ```solidity
  // Ath Staking contract
  IAthStaking public athStaking;
  ```
* ```solidity
  // DEV TEAM Address
  address public devAddress;
  ```
* ```solidity
  // List investors
  address[] private investorList;
  ```
* ```solidity
  // pre-sale start time
  uint256 public startTime;
  ```
* ```solidity
  // pre-sale end time
  uint256 public endTime;
  ```
* ```solidity
  // funding Period
  uint256 public fundingPeriod;
  ```
* ```solidity
  // Price of each token
  uint256 public price;
  ```
* ```solidity
  // Amount of tokens remaining    
  uint256 public availableTokens;
  ```
* ```solidity
  // Total amount of tokens to be sold    
  uint256 public totalAmount;
  ```
* ```solidity
  // Total amount sold
  uint256 public totalAmountSold;
  ```
* ```solidity
  // Release time
  uint256 public releaseTime;
  ```
* ```solidity
  // Release time 
  uint256 public releaseTime;
  ```
* ```solidity
  // total collected Fee 
  uint256 public collectedFee;
  ```
* ```solidity
  // total fund rasied 
  uint256 public totalFundRaised;
  ```
* ```solidity
  // total pre-sale token suppiled 
  uint256 public totalIDOTokenSupplied;
  ```
* ```solidity
  // total pre-sale token claimed by user
  uint256 public totalIDOTokenClaimed;
  ```
* <pre class="language-solidity"><code class="lang-solidity">// Number of investors
  <strong>uint256 public numberParticipants;
  </strong></code></pre>

Mapping variables

* ```solidity
  // Info of each investor that buy tokens.
      mapping(address => Sale) public sales;
  ```
* ```solidity
  // Amount of tokens remaining w.r.t Tier
  mapping(uint8 => uint256) public tierMaxAmountThatCanBeInvested;
  ```
* ```solidity
  // Participation fee based on Ath Staking Level
  mapping(uint8 => uint256) public participationFee;
  ```
