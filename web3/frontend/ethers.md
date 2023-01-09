---
title: ethers.js
tags:
  - web3
  - development
  - frontend
---

[`ethers.js`](https://docs.ethers.io/v5/) is a library for interacting with an [[Ethereum network]] and its ecosystem.

- [[web3/frontend/Signers]]
- [[Providers]]

## `gasLimit`

In `ethers` it's possible to limit how much of gas the users may pay for calling the function.

```ts
contract.functionToCall(message, { gasLimit: 300000 });
```

This way makes the user pay a set amount of gas of 300,000. I he don't use all of it in the transaction he'll automatically be refunded (if a transaction costs 250,000 gas then after that transaction is finalized that 50,000 gas left over that the user didn't use will be refunded).
