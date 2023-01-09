---
title: ABI
---

By definition, an `ABI` (or _Application Binary Interface_) is the interface of interoperability of compiled software (hence _binary_).

In [[EVM]] [[web3/Smart contracts]] need to be compiled from e.g. [[web3/solidity/Solidity]] to EVMs bytecode. The smart contract is just this sequence of bytecode. To access functions defined in high-level languages, users need to translate names and arguments into byte representations for byte code to work with it. The ABI documents these names and types precisely, easily parseable format, doing translations between human-intended method calls and smart-contract operations discoverable and reliable.

In other words, when you compile your smart contract, the compiler spits out a bunch of files needed that lets you interact with the contract. The files are basically the ABI.

In [[web3/solidity/Hardhat]] compiled ABI lies under `artifacts/contracts/<contractName>.sol/<contractName>.json`.

## Resources

- https://www.quicknode.com/guides/smart-contract-development/what-is-an-abi
- https://docs.soliditylang.org/en/v0.8.14/abi-spec.html
