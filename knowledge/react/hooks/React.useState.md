# `React.useState`

> 💡 Hooki są zajebiste. - Łukasz Pluszczewski

`const [variable, setVariable] = useState(initialValue)`

To `setVariable` function we can pass both value and the function that takes previous value as the argument. The calculated value will be set to the _hooked_ variable:

```js
setVariable(5);
setVariable((prevValue) => prevValue + 1);
```

[React](/Knowledge/React/index.md)'s' `useState` and `setState` don’t make changes directly to the `state`. They create queues to optimise performance, which is why the changes don’t update immediately. The process to update React state is asynchronous for performance reasons.

The `useState` hook cannot be called conditionally. The exact number of calls and the order of the calls have to be the same in **every component render**. They can be used in callbacks, in loops, in another functions.

An exception: hooks may be used in [custom hooks](Knowledge/React/hooks/custom%20hooks.md).

To perform side effects after state has change, you must use the [`useEffect`](Knowledge/React/hooks/React.useEffect.md).
