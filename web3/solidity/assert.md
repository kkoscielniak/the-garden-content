---
title: assert fn
---

`assert` is similar to [[web3/solidity/require]]. The difference between `assert` and `require` is that `require` will refund the user the rest of their gas when a function fails, **whereas `assert` will not**.

Most of the time you want to use `require` in your code; `assert` is typically used when something has gone horribly wrong with the code (like the [[web3/solidity/overflows]]).
