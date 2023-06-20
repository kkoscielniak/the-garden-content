---
title: moize
---

[useMemo](/knowledge/react/useMemo.md) has its limits - for example if we're [memoizing](/memoization) the same results but in different components:

```jsx
const n = 1;
// ...
const finA = useMemo(() => fibonacci(n), [n]);
const finB = useMemo(() => fibonacci(n), [n]);
```

These second result will be evaluated independently of the fact that value was already calculated.

`useMemo` keeps the result only for the component.

This can be remedated using [moize](https://github.com/planttheidea/moize/) library:

```js
const moizedFibonacci = moize(fibonacci);
const finC = useMemo(() => moizedFibonacci(n));
```