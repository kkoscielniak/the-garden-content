---
title: useCallback
---

Each time we rerender the component, the callback functions are recreated.

The `useCallback` hook is used to make functions recreate only if the dependencies change (similarly to [useEffect](/useEffect) and [useMemo](/knowledge/React/useMemo.md)).

We could use `useCallback` to [memoize](/memoization) the [render-props](/knowledge/React/render-props.md) `render` fn for future uses (as long as the dependencies don't change).
