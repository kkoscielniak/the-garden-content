---
title: useCallback
---

Each time we rerender the component, the callback functions are recreated.

The `useCallback` hook is used to make functions recreate only if the dependencies change (similarly to [[useEffect]] and [[knowledge/react/useMemo]]).

We could use `useCallback` to [[memoization|memoize]] the [[knowledge/react/render-props]] `render` fn for future uses (as long as the dependencies don't change).
