---
title: useMemo
---

`useMemo` is a hook allowing to save the returned value of time-consuming, costful function between subsequent rerenders.

This process is called [[memoization]].

We can define dependencies that will cause re-evaluation of the value if these dependencies change.
