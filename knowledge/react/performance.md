---
title: Performance optimisation in React
---

# Performance optimisation in [React](Knowledge/React/index.md)
- **minimize the number of updates**
- use [React.Fragment](Knowledge/React/React.Fragment.md) to optimize both [virtual-dom](Knowledge/React/virtual-dom.md) and the [real one](Knowledge/WebDev/DOM.md)
- Virtualize long lists with [react-window](Knowledge/React/react-window.md) (or else)
- [Lazy-load](Knowledge/React/React.lazy().md) the components once they are needed
- use [Code splitting](Knowledge/React/Code%20splitting.md) to reduce initial load time
- [memoize](Knowledge/React/useMemo.md) the [Pure Components](Knowledge/React/pure-component.md)
- use [key](Knowledge/React/key.md) prop properly
- use [useCallback](Knowledge/React/useCallback.md) hook to stop unnecessary re-renders 
- use Server-Side Rendering to reduce the Initial Page Load
- optimize Images Loading
	- compress them
	- use appropriate image formats
	- use responsive images
	- lazy load them
	- use CDN if possible
- avoid inline-styling, use pre-processors or CSS-in-JS libs instead
	- optimize CSS with PurgeCSS or PostCSS