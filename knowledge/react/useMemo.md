---
title: useMemo
---

`useMemo` is a hook allowing to save the returned value of time-consuming, costful function between subsequent rerenders. 

This process is called [memoisation](/Knowledge/Performance/memoisation.md).

We can define dependencies array that will cause re-evaluation of the memoised value once these dependencies change.

## Resources
- [react-memo](Knowledge/React/react-memo.md)
- [moize](Knowledge/React/packages/moize.md)