---
title: Higher Order Components
---

_Higher Order Components_ is a [pattern](/pattern) in [React](/development/react/_index) allowing to enhance the component with additional logic (like authentication, state).

A HOC in that regard is a component that wraps the enhanced one:

```js
const withHoc = (StatelessComponent) => {
  const Wrapper = (props) => {
    const { children } = props;
    const [on, setOn] = useState(false);
    const toggle = () => setOn((prevState) => !prevState);

    return (
      <StatelessComponent on={on} toggle={toggle} {...props}>
        {children}
      </StatelessComponent>
    );
  };

  return Wrapper;
};

const EnhancedComponent = withHoc(WrappedComponent);
```

This way we write less repetitive code.

HOCs have advantages, such as:

- they don't change the wrapped components
  - allowing to focus on [Presentational components](/Knowledge/React/containers-vs-presentation-components.md)
- they simplify testing the application

We can nest HOC wrapping, but we need to be mindful about the order of such operations.

The concept of HOCs has its roots in the [functional-programming](/functional-programming) [higher-order-fns](/higher-order-fns).
