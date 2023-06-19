---
title: Reconciliation
---

_Reconciliation_ is the algorithm used by [[development/react/_index|React]] every time it has to rerender the application.

Initially, when we define the application structure (first render), React goes through the components and builds a tree of them. This tree defines that structure of ours.

It goes from parents to children and then back to parents to confirm the integrity of the components on every level.

Then it builds the DOM tree of the components in the _structure tree_ in a form of HTML tags.

Once we modify any of the the component in the application, React checks if it should rerender said component (`shouldComponentUpdate`, checks if component is pure, has `React.memo` etc.). It also goes to children to see if the changes affect them.

Based on that React builds list of things to rerender. After that both _structure tree_ and DOM tree are _reconciled_ and the DOM tree gets rerendered.

There are two phases of the commit:

1. Rendering - checking if the particular component has to be rerendered (and doing so if needed)
2. Commit - checking if children have to be rerendered and verifying their integrity

> [!tip] To make sure the app is rerendered properly, when we render the lists, we need the `key` prop.

In React for web reconciliation is a responsibility of `react-dom` package.
