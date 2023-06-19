---
title: "`children` prop"
---

The _usual_ way of using `children`:

```jsx
<Header>
  <ChildComponent truthy />
</Header>
```

is a syntax sugar for:

```jsx
<Header children={[<ChildComponent truthy />]} />
```

We can see that this syntax is similar to how the [[knowledge/react/render-props]] are used.

---

We can use the `children` prop to avoid [[knowledge/react/prop-drilling]] (we add props to the child component and don't have to pull `truthy` prop in the `<Header />` component implementation.

---

We can use `React.Children.count(children)` helper to make sure how much `children` have been passed to the component.

`React.Children.map(children)` handles mapping of `children` independently of the number of the child components.
