---
title: view function modifier
tags:
  - development
  - solidity
  - web3
---

A `view` function modifier in [[web3/solidity/Solidity]] denotes a function used for _reading_ data from the [[web3/Smart contracts|smart contract]].

When we read data from the smart contract, no [[web3/transaction]] is made and the [[web3/ethereum/gas-fee]] is not applied, since we're not making any changes to the [[web3/blockchain]].

```solidity
function getAllWaves() public view returns (Wave[] memory) {
    return waves;
}
```
