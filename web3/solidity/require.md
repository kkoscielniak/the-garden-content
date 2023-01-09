---
title: require function
tags:
  - web3
  - development
---

`require` [[web3/solidity/function]] checks if the condition passed as an argument is `true`.

If it's not, the function will quit and the [[web3/transaction]] will cancel.

## Example

```solidity
require(
    prizeAmount <= address(this).balance, // condition
    "Trying to withdraw more money than the contract has." // error message
);
```
