---
title: payable modifier
---

`payable` denotes a function that can fund the [[web3/smart-contracts|contract]] and payout money from it to the users interacting with it.

```solidity
constructor() payable {
  console.log("We have been constructed!");
}
```

Missing the `payable` will cause `Non-payable constructor cannot override value` error.

## References

- [[web3/solidity/Hardhat#`console.log`|console.log]]
