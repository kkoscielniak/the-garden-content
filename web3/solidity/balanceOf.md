---
title: balanceOf function
tags:
- web3
- development
---
In [[Solidity]], the `balanceOf` function simply takes an `address`, and returns how many tokens that `address` owns.

```solidity
  function balanceOf(address _owner) external view returns (uint256 _balance);
```