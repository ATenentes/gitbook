---
description: How smartcontract are organized
---

# Smartcontract Logic

Smartcontracts for athenadexfi can be found at the following repository:

{% hint style="info" %}
[https://github.com/AthenaDexFi/athena-smartcontract](https://github.com/AthenaDexFi/athena-smartcontract)
{% endhint %}

Smartcontract are using hardhat framework for testing and deployment

### Trader Feature Contracts

{% hint style="success" %}
[https://miro.com/app/board/uXjVNa6JHyQ=/?share\_link\_id=314673237168](https://miro.com/app/board/uXjVNa6JHyQ=/?share\_link\_id=314673237168)
{% endhint %}

* QueueFactory ( Where user interact to deploy his trading contract )
* Short Factory ( In case short features is triggered this contract deploy a fresh instance of a short contract )
* QueueInfo ( where traders, queue and short contracts are mapped )
* AthQueue ( Deployed Contract from the Queue Factory where the user can collect money and distribute rewards )
* AthTrader ( Deployed Contract from the AthQueue that allow user to perform swaps on varius DEX )
* AthShort ( Deployed Contract from the ShortFactory, allow AthTrader contract to perform borrowing and lending on venus protocol )



### Presale Contracts

* AthenaPoolFactory ( Where launchpads are configured by the admin )
* AthenaLaunchpadInfo ( Where launchpads are mapped )
* IDO Pool ( The contract deployed by the pool factory )



### Various Contracts

* AthToken ( Simple ERC20 Token )
* AthReferral ( Referral System for trading contracts )
* AthStaking ( Where users can stake their ath token to increase their Ath Level in order to get benefits )

