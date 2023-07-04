---
title: moize
---

[useMemo](/Knowledge/React/useMemo.md) has its limits - for example if we're [memoizing](/Knowledge/Performance/memoisation.md) the same results but in different components:

```jsx
const n = 1;
// ...
const finA = useMemo(() => fibonacci(n), [n]);
const finB = useMemo(() => fibonacci(n), [n]);
```

These second result will be evaluated independently of the fact that value was already calculated.

`useMemo` keeps the result only for the component.

This can be remediated using [moize](/Knowledge/React/packages/moize.md) library:

```js
const moizedFibonacci = moize(fibonacci);
const finC = useMemo(() => moizedFibonacci(n));
```
