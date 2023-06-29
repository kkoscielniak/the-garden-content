---
title: event
---

On a basic level, an `event` in [index](/Knowledge/Web3/solidity/index.md) is a message the [smart-contracts](/Knowledge/Web3/smart-contracts.md) throw out that can be captured in a client **in real time**.

## Example

```solidity
// defining an event
event NewWave(address indexed from, uint256 timestamp, string message);

// calling an event
emit NewWave(msg.sender, block.timestamp, _message);
```
