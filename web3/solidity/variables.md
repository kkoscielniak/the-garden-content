---
title: variable types
tags:
  - web3
  - solidity
---

In [[web3/solidity/Solidity]], there are two locations you can store variables — in `storage` and in `memory`.

`storage` variables are stored permanently on the [[blockchain]]. `memory` variables are temporary, and disappear when the function call ends.

Most of the time Solidity will handle them by default. [[web3/solidity/state-variable]]s are by default `storage`. Variables declared inside functions are `memory`.

However, variables have to be declared as `storage` or `memory` when dealing with [[struct]]s and [[array]]s within functions.

```solidity
contract SandwichFactory {
  struct Sandwich {
    string name;
    string status;
  }

  Sandwich[] sandwiches;

  function eatSandwich(uint _index) public {
    // You should declare with the `storage` keyword, like:
    Sandwich storage mySandwich = sandwiches[_index];

    // ...in which case `mySandwich` is a pointer to `sandwiches[_index]`
    // in storage, and...

    mySandwich.status = "Eaten!";
    // ...this will permanently change `sandwiches[_index]` on the blockchain.

    // If you just want a copy, you can use `memory`:
    Sandwich memory anotherSandwich = sandwiches[_index + 1];
    // ...in which case `anotherSandwich` will simply be a copy of the
    // data in memory, and...
    anotherSandwich.status = "Eaten!";
    // ...will just modify the temporary variable and have no effect
    // on `sandwiches[_index + 1]`. But you can do this:
    sandwiches[_index + 1] = anotherSandwich;
    // ...if you want to copy the changes back into blockchain storage.
  }
}
```
