---
title: require function
---

`require` [function](/Knowledge/Web3/solidity/function.md) checks if the condition passed as an argument is `true`.

If it's not, the function will quit and the [transaction](/Knowledge/Web3/transaction.md) will cancel.

## Example

```solidity
require(
    prizeAmount <= address(this).balance, // condition
    "Trying to withdraw more money than the contract has." // error message
);
```
