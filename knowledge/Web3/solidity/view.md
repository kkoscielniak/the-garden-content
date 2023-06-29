---
title: view function modifier
---

A `view` function modifier in [index](/Knowledge/Web3/solidity/index.md) denotes a function used for _reading_ data from the [smart contract](/Knowledge/Web3/smart-contracts.md).

When we read data from the smart contract, no [transaction](/Knowledge/Web3/transaction.md) is made and the [gas-fee](/Knowledge/Web3/ethereum/gas-fee.md) is not applied, since we're not making any changes to the [blockchain](/Knowledge/Web3/blockchain.md).

```solidity
function getAllWaves() public view returns (Wave[] memory) {
    return waves;
}
```
