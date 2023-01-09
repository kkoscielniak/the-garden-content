---
title: event
tags:
  - web3
  - development
---

On a basic level, an `event` in [[web3/solidity/Solidity]] is a message the [[web3/Smart contracts|smart contract]] throw out that can be captured in a client **in real time**.

## Example

```solidity
// defining an event
event NewWave(address indexed from, uint256 timestamp, string message);

// calling an event
emit NewWave(msg.sender, block.timestamp, _message);
```
