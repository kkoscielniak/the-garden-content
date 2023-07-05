## Functional Components Lifecycle

Class components live as long as the class instance lives, so the state is preserved between the subsequent re-renders.

Functional Components live as long as the rendering takes time. **There is no instance**. Once they get mounted, the component function is deleted (it has fulfilled its purpose).

In that sense, functional components are basically the `render` functions of the [class components](Knowledge/React/class-components.md). They live **JUST** during the rendering. The variables are recreated on each render, so it's unable to keep the state, side effects, refs to HTML etc. without using [hooks](/Knowledge/React/hooks.md).

- [[Knowledge/React/hooks/React.useState]]
- [[Knowledge/React/hooks/React.useEffect]]
- [[Knowledge/React/hooks/React.useRef]]
- [[Knowledge/React/hooks/React.useContext]]
- [[Knowledge/React/hooks/React.useReducer]]
- [[Knowledge/React/hooks/hook-rules]]
- [custom hooks](Knowledge/React/hooks/custom%20hooks.md)