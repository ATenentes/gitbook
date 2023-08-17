---
description: List of Variables which is used by AthenaPoolFactory smart contract.
---

# event

```solidity
Buy
```

* ```solidity
  event Buy(address indexed _user, uint256 _amount, uint256 fee, uint256 _tokenAmount);
  ```

```solidity
Claim
```

* ```solidity
  event Claim(address indexed _user, uint256 _amount)
  ```

```
Withdraw
```

* ```solidity
  event Withdraw(address indexed _user, uint256 _amount);
  ```

```
EmergencyWithdraw
```

* ```solidity
  event EmergencyWithdraw(address indexed _user, uint256 _amount);
  ```

```
TokenRecovered
```

* ```solidity
  event TokenRecovered(address indexed _user, address indexed _token, uint256 _amount);
  ```

```
TokenAddressUpdated
```

* ```solidity
  event TokenAddressUpdated(address indexed _user, address indexed _token);
  ```

```
AthStakingUpdated
```

* ```solidity
  event AthStakingUpdated(address indexed _user, address _oldStaking, address _newStaking);
  ```

```
DevAddressUpdated
```

* ```solidity
   event DevAddressUpdated(address indexed _user, address _oldDev, address _newDev);
  ```

```
IDOTokenSupplied
```

* ```solidity
  event (address indexed _user, uint256 _amount);
  ```
