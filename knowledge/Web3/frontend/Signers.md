---
title: Signers
---

In [ethers](/knowledge/Web3/frontend/ethers.md) a _Signer_ is an abstraction of an [Ethereum](/Ethereum) account, which can be used to sign transactions and send signed transactions to the [Ethereum Network](/Ethereum%20Network) to execute state changing operations.

The available operations depend largely on the sub-class used.

The most common Signers are:

- `Wallet`, which is a class which knows a [crypto-wallet](/knowledge/Web3/crypto-wallet.md) private key and can execute any operations with it
- [JsonRpcSigner](/JsonRpcSigner), which is connected to a JsonRpcProvider (or sub-class) and is acquired using `getSigner()`
