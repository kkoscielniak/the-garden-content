---
title: event
---

On a basic level, an `event` in [[web3/solidity/_index]] is a message the [[web3/smart-contracts]] throw out that can be captured in a client **in real time**.

## Example

```solidity
// defining an event
event NewWave(address indexed from, uint256 timestamp, string message);

// calling an event
emit NewWave(msg.sender, block.timestamp, _message);
```
