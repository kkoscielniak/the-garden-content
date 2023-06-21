---
title: view function modifier
---

A `view` function modifier in [index](/knowledge/Web3/solidity/index.md) denotes a function used for _reading_ data from the [smart contract](/knowledge/Web3/smart-contracts.md).

When we read data from the smart contract, no [transaction](/knowledge/Web3/transaction.md) is made and the [gas-fee](/knowledge/Web3/ethereum/gas-fee.md) is not applied, since we're not making any changes to the [blockchain](/knowledge/Web3/blockchain.md).

```solidity
function getAllWaves() public view returns (Wave[] memory) {
    return waves;
}
```
