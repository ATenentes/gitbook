---
description: Deployment Arguments
---

# AthenaNFTPresale

```
_partecipationNFTAddress Address of the PartecipationNFT contract.
_athStaking Address of the AthStaking contract to fetch user level.
Array:
athLevels User ATH levels.
athDiscount Fees discount for each ATH level. 10% = 1000
_minRequiredAthLevel Minimum ATHLevel to partecipate ( 0, 1, 2 , 3)
```

## Presale Start \[ADMIN]

1. **Call setRaiseParameters function**

* &#x20;\_raiseToken Address of the ERC20 token used for raising.
* &#x20;\_amountToRaise Total amount to raise.
* &#x20;\_raiseStartTime Start time of the raise. ( UNIX TIMESTAMP )
* \_minContribution Minimum contribution per user.
* \_maxContribution Maximum contribution per user.

2. **Call setPresaleAttributes function**

* \_presaleName Name of the presale.
* \_presaleID ID of the presale. ( must be unique for each presale )
* \_redeemFees Redeem fees. ( base fee for redeem )
* \_sellFees Sell fees. ( for marketplace purpose in future )

3. **Call setAthLevelDiscount function (OPTIONAL)**

It will set the discount based for each user level. Example \[ 0,1,2,3 ] \[ 1000,2000,3000,4000] means 10% discount for level 0, 20% for level 1 ecc

* level\_ index of level
* \_ fee defined in percentage for given level



## Presale Management \[ADMIN]

### **finalizeRaise function**

* true = the raise is set as  succesfull and admin can claim funds&#x20;
* false = the raise is set as unsucesfull and users can claimBack funds



### withdrawFunds function

allow the admin to claim the funds raised into the smartcontract, transfering to the admin wallet



### topUp function (amount)

Allows the admin to top up the contract with raiseToken for rewards and cashback.

When the total top-up amount is still below the total raised amount (refundReady is false),the top-up amount first goes to the cashback pool. Once the cashback pool is full (totalRefund equals totalRaised), refundReady is set to true, and subsequent top-ups are used for rewards and are subject to fee deductions based on each NFT holder's athLevel.



### Emits a TopUp event.

### Requirements:

&#x20;\- The caller must be the admin of the contract.

&#x20;\- The fundraise must have been marked successful.

&#x20;\- Rewards must not already have been distributed.

&#x20;\- If refundReady is true, the excess amount must be greater than total fees calculated

### distributeRewards function

Allows the admin to mark rewards as ready to be distribute. From now users can start burning their NFT to start the claimReward.

### forceEnableRefund function

Allow admin to force the enable refund in case the sell of tokens is not covering the original raised amount.User can call claimRefund.



## User Actions \[PUBLIC]

### partecipate function (amount)

User can partecipate with an amount included between min amount and max amount. Also his level should be equal or greater than the one setted by the admin.&#x20;

### claimBack function

If admin setted the raise as unsuccessful the users can claim back their partecipated amount

### claimPartecipationNFT function

If admin setted the raise as sucesfull the users can claim their partecipation NFT with all the relevant datas.

### claimRefund function

After the topup from the admin will cover the initial partecipationamount the users can call this function to get back without any taxation their initial investment.

### claimRewards function

after admin call the distributeRewards function users can claim their extra profit netted of fees and burn their own NFT\
