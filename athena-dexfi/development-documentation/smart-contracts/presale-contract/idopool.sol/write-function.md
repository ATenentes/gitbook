---
description: List of write functions.
---

# Write Function

External

* ````solidity
  ```solidity
  /**
  * @dev To withdraw tokens after the sale ends and burns the remaining tokens
  *
  * Requirements:
  * - invocation can be done, only by the contract owner.
  * - the public sale must have ended
  * - this call is non reentrant
  */
  function withdraw() external onlyOwner publicSaleEnded nonReentrant {
     if (availableTokens > 0) {
         availableTokens = 0;
     }

     transferCurrencyToken();
  }
  ```
  ````
* ````solidity
  ```solidity
  /**
   * @dev To withdraw in case of any possible hack/vulnerability
   *
   * Requirements:
   * - invocation can be done, only by the contract owner.
   * - this call is non reentrant
   */
  function emergencyWithdraw() external onlyOwner nonReentrant {
      if (availableTokens > 0) {
          availableTokens = 0;
      }

      if (totalIDOTokenSupplied > 0 &&
          totalIDOTokenSupplied > totalIDOTokenClaimed) {
              token.transfer(owner(), totalIDOTokenSupplied.sub(totalIDOTokenClaimed));
      }
      transferCurrencyToken();
  }
  ```
  ````
* ````solidity
  ```solidity
  /**
   * @dev To add users and tiers to the contract storage
   * @param _participationFees An array of participation fee as per tiers
   * @param _maxAmountThatCanBeInvestedInTiers An array of max investments amount in tiers
   */
  function setTierInfo(
          uint256[] memory _participationFees,
          uint256[] memory _maxAmountThatCanBeInvestedInTiers
  )
      public onlyOwner
  {
      for (uint8 i = 0; i < _maxAmountThatCanBeInvestedInTiers.length; i++) {
          require(_maxAmountThatCanBeInvestedInTiers[i] > 0, "Tier allocation amount must be > 0");
          // Since we have named Tier1, Tier2, Tier3 & Tier4
          tierMaxAmountThatCanBeInvested[i + 1] = _maxAmountThatCanBeInvestedInTiers[i];
          participationFee[i + 1] = _participationFees[i];
      }
  }
  ```
  ````
* ```solidity
  /**
   * @dev To set the Ath Staking address
   * @param _athStaking ath staking contract address
   */
  function setAthStaking(address _athStaking) external onlyOwner {
      require(_athStaking != address(0x0), "_athStaking should be valid address");

      emit AthStakingUpdated(msg.sender, address(athStaking), _athStaking);
      athStaking = IAthStaking(_athStaking);
  }
  ```
* ```solidity
  /**
   * @dev To set the DEV address
   * @param _devAddr dev wallet address.
   */
  function setDevAddress(address _devAddr) external onlyOwner {
      require(_devAddr != address(0x0), "_devAddr should be valid Address");

      emit DevAddressUpdated(msg.sender, devAddress, _devAddr);
      devAddress = _devAddr;
  }
  ```
* ```solidity
  /**
   * @dev To set the Token address
   * @param _token token address.
   */
  function setTokenAddress(address _token) external onlyOwner {
      require(_token != address(0x0), "_token should be valid Address");

      token = IERC20(_token);
      tokenDecimal = token.decimals();

      emit TokenAddressUpdated(msg.sender, _token);
  }
  ```
* ```solidity
  /**
  * @dev To recover ERC20 token sent to contract by mistake
  * @param _tokenAddress ERC20 token address which need to recover
  * @param _amount amount of token to be recover
  */
  function recoverToken(address _tokenAddress, uint256 _amount) external onlyOwner {
     IERC20 _token = IERC20(_tokenAddress);
     _token.safeTransfer(msg.sender, _amount);

     emit TokenRecovered(msg.sender, _tokenAddress, _amount);
  }
  ```
* ```solidity
  /**
  * @dev To supply IDO token to contract
  * @param _amount amount of token to be supplied to contract
  */
  function supplyIDOToken(uint256 _amount) external onlyOwner {
  require(totalIDOTokenSupplied.add(_amount) <= totalAmountSold,
          "IDO token amount is overflooded!!");

  token.safeTransferFrom(msg.sender, address(this), _amount);
  totalIDOTokenSupplied += _amount;

  emit IDOTokenSupplied(msg.sender, _amount);
  }
  ```
* ````solidity
  ```solidity
  /**
  * @dev To buy tokens
  *
  * @param amount The amount of tokens to buy
  *
  * Requirements:
  * - can be invoked only when the public sale is active
  * - this call is non reentrant
  */
  function buy(uint256 amount) external publicSaleActive nonReentrant {
  require(availableTokens > 0,
          "All tokens were purchased");

  require(amount > 0,
          "Amount must be > 0");


  require(currency.balanceOf(msg.sender) >= amount,
          "Insufficient currency balance of caller");

  InvestorType investorType = getInvestorType(msg.sender);
  require(isParticipationTimeCrossed(investorType),
          "Participation time is not yet crossed. Please wait.");

  uint8 tier = uint8(investorType) + 1;
  uint256 fee = amount.mul(participationFee[tier]).div(10000);
  if (fee > 0) {
      collectedFee = collectedFee.add(fee);
  }

  uint256 amountAfterFee = amount.sub(fee);
  uint256 allocatedToken = (amountAfterFee).mul(10 ** tokenDecimal).div(price);

  require(allocatedToken <= availableTokens,
          "Not enough tokens to buy");

  Sale storage sale = sales[msg.sender];
  require(sale.allocatedAmount.add(allocatedToken) <= tierMaxAmountThatCanBeInvested[tier],
          "amount exceeds buy limit");

  availableTokens = availableTokens.sub(allocatedToken);
  totalAmountSold = totalAmountSold.add(allocatedToken);
  totalFundRaised = totalFundRaised.add(amountAfterFee);

  currency.safeTransferFrom(msg.sender, address(this), amount);

  if (sale.allocatedAmount == 0) {
      sales[msg.sender] = Sale(msg.sender,
                                  amount,
                                  fee,
                                  allocatedToken,
                                  0,
                                  false);
      numberParticipants += 1;
      investorList.push(msg.sender);
  } else {
      sales[msg.sender] = Sale(msg.sender,
                                  sale.amount.add(amount),
                                  sale.feePaid.add(fee),
                                  sale.allocatedAmount.add(allocatedToken),
                                  0,
                                  false);
  }

  emit Buy(msg.sender, amount, fee, allocatedToken);
  }
  ```
  ````
* ```solidity
  /**
   * @dev To withdraw purchased tokens after release time
   *
   * Requirements:
   * - this call is non reentrant
   * - cannot claim within release time
   */
  function claimTokens() external canClaim nonReentrant {
      Sale storage sale = sales[msg.sender];
      require(!sale.tokenWithdrawnStatus, "Already withdrawn");
      require(sale.allocatedAmount > 0, "Only investors");

      uint256 tokenAmount = claimableAmount(msg.sender);
      token.transfer(sale.investor, tokenAmount);

      sale.tokensWithdrawn += tokenAmount;
      totalIDOTokenClaimed += tokenAmount;
      if (sale.tokensWithdrawn == sale.allocatedAmount) {
          sale.tokenWithdrawnStatus = true;
      }

      emit Claim(msg.sender, tokenAmount);
  }
  ```

#### Internal

* ```solidity
  /**
   * @dev To transfer Currency token
   */
  function transferCurrencyToken() internal {
      uint256 currencyBalance = currency.balanceOf(address(this));

      currency.safeTransfer(owner(), collectedFee);
      emit Withdraw(owner(), collectedFee);

      currency.safeTransfer(devAddress, currencyBalance.sub(collectedFee));
      emit Withdraw(devAddress, currencyBalance.sub(collectedFee));
  }
  ```
