---
title: useCallback
---

Each time we rerender the component, the callback functions are recreated.

The `useCallback` hook is used to make functions recreate only if the dependencies change (similarly to [useEffect](/useEffect) and [useMemo](/Knowledge/React/useMemo.md)).

We could use `useCallback` to [memoize](/Knowledge/Performance/memoisation.md) the [render-props](/Knowledge/React/render-props.md) `render` fn for future uses (as long as the dependencies don't change).
