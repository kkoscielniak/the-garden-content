---
title: Smart contracts
---

Smart contracts are programs which govern the behaviour of accounts within the Ethereum state.

In other words they can be treated as the server-side code with different API endpoints (functions) people can hit.

Practically the basis of most smart contracts is:

- read functions
- write functions
- change the [state-variable](/Knowledge/Web3/solidity/state-variable.md)s

> [!tip]
>
> Smart contracts are lines of code that automatically execute a function when given an input — just like a vending machine.

## Immutability

Smart contracts are immutable by design. Once they are deployed, they stay in their state permanently. Changing a contract requires a full redeploy. The redeploy also resets all the variables since newly deployed contract is treawted a **brand new contract**.

New contract means **new address**, and both address and [ABI](/Knowledge/Web3/ABI.md) have to be updated on the [index](/Knowledge/Web3/frontend/index.md) side.

> [!tip] This can be solved
>
> The immutability ifself is a feature, however some parts of the contract can be deliberately programmed to be changeable (e.g. with the [ownable contract](/ownable%20contract)).
>
> - [ ] Learn and describe how to solve it.

## Deploying the smart contract

Deployment of the smart contract is considered a [transaction](/Knowledge/Web3/transaction.md).

When we deploy our contract, we tell all miners to add smart contract to the blockchain and to broadcast the contract creation transaction over the whole [blockchain](/Knowledge/Web3/blockchain.md).

Once the transaction is mined, it is then broadcasted to the blockchain as a legit transaction. From there, everyone updates their copy of the blockchain.