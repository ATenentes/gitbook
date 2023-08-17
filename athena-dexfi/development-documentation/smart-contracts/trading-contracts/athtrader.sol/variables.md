---
description: List of Variables which is used by AthTrade contract.
---

# Variables

Variables

* ```solidity

      address public owner; // Address of AthTrader owner
  ```
* ```solidity
  // Address of AthStaking contract
  address public immutable athLevel;
  ```
* ```solidity
  // Address of Gelato Core module
  address public immutable gelatoCore = 0x0c30D3d66bc7C73A83fdA929888c34dcb24FD599;
  ```
* ```solidity
  // Address of Gelato for ERC20 swaps
  address  public immutable gelatoERC20Router = 0x64c7f3c2C19B41a6aD67bb5f4edc8EdbB3284F34;
  ```
* ```solidity
  // Address of pancake Router contract
  address public immutable allowedRouter = 0x10ED43C718714eb63d5aA57B78B54704E256024E;
  ```
* ```solidity
  // Address of trader account
  address public trader;
  ```
* ```solidity
  // Address of traderFactory
  address public traderFactory;
  ```
* ```solidity
  // Address of ShortOrder contract
  address public shortOrderContract;
  ```
* ```solidity
  // Trader fee defined in percentage
  uint8 public traderFee;
  ```
* ```solidity
  // Status of emergency withdraw
  bool public isEmergencyWithdrawlEnabled;
  ```
* ```solidity
  // Address of participation token contract
  address public participationToken;
  ```
* ```solidity
  // Funding start time defined in timestamp
  uint256 public fundingStartTime;
  ```
* ```solidity
  // Funding period defined in seconds
  uint256 public fundingPeriod;
  ```
* ```solidity
  // Trading period defined in seconds
  uint256 public tradingPeriod;
  ```
* ```solidity
  // Claiming period defined in seconds
  uint256 public claimingPeriod;
  ```
* ```solidity
  // Benchmark for total funding amount
  uint256 public fundingCap;
  ```
* ```solidity
  // Minimum contribution required to participate in funding round
  uint256 public minContribution;
  ```
* ```solidity
  // Total invested amount of participated token
  uint256 public totalInvestment;
  ```
* ```solidity
  // Total amount of participated token Post trading Period
  uint256 public concludedTotalAmount;
  ```
* ```solidity
  // Reward rate for calculating harvested amount
  uint256 public rewardRate;
  ```
* ```solidity
  // bool check to verify contract is concluded or not
  bool public isTradingContractConcluded;
  ```
* ```solidity
  // traded token array
  address[] public tradedToken;
  ```
* ```solidity
  /**
   * @dev array containing vaults of Gelato's orders
   */
  address[] public gelatoVaults;
  ```

Mapping variables

* ```solidity
  /**
  * @dev Returns true if given address is allowed for trading
  */
     mapping(address => bool) public allowedTokens;
  ```
* ```solidity
  /**
      * @dev Returns invested amount for given address
      */
     mapping(address => uint256) public investedAmount;
  ```
* ```solidity
  /**
      * @dev Returns claimed amount of given address
      */
     mapping(address => uint256) public userClaimedAmount;
  ```
* ```solidity
  /**
      * @dev Returns traded Token index of array
      */
     mapping(address => uint256) public tradedTokenMap;
  ```
* ```solidity
  /**
      * @dev Returns the token used in the given vault
      */
     mapping(address => address) public gelatoVaultToken;
  ```
* ```solidity
  /**
      * @dev Returns referrer  of given address
      */
     mapping(address => address) public referrer;
  ```
