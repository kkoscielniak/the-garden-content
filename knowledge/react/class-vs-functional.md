---
title: Class vs Functional components
---

We have 2 types of components in [React](/Knowledge/React/index.md).

## Class Components

- Class-based Components uses ES6 `class` syntax. It can make use of the [lifecycle](/Knowledge/React/lifecycle.md) methods
- Class components extend from `React.Component`
- You have to use `this` keyword to access the props and functions that you declare inside the class components

## Functional Components

- simpler to write comparing to class-based functions
- mainly focus on the UI of the application, not on the behavior
- these are basically `render()` from the class component
- can have state and mimic lifecycle events using [hooks](/Knowledge/React/hooks.md)
