## Functional Components Lifecycle

Class components live as long as the class instance lives, so the state is preserved between the subsequent re-renders.

Function component is basically the sole `render` function. So it lives **JUST** during the rendering. The variables are recreated on each render, so it's unable to keep the state/references to HTML etc. without using [hooks](/Knowledge/React/hooks.md).
