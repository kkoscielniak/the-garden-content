---
title: Signers
tags:
  - web3
  - development
---

In [[ethers]] a _Signer_ is an abstraction of an [[Ethereum]] account, which can be used to sign transactions and send signed transactions to the [[Ethereum Network]] to execute state changing operations.

The available operations depend largely on the sub-class used.

The most common Signers are:

- [[Wallet]], which is a class which knows a [[web3/crypto-wallet]] private key and can execute any operations with it
- [[JsonRpcSigner]], which is connected to a JsonRpcProvider (or sub-class) and is acquired using `getSigner()`
