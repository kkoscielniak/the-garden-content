---
title: React Lifecycle phases and methods
---

For [class-components](/class-components):

## Initialisation

[React](/Knowledge/React/index.md) component prepares setting up the initial `state` and default `props`.

## Mounting

Creating a corresponding DOM element and connecting to it.

- `render`
- `componentWillMount`
  - before rendering
- `componentDidMount`
  - after first rendering
  - all AJAX requests, DOM or state updates, and set up eventListeners should occur here

## Updating

Sending new props or updating the state.

- `componentWillReceiveProps`
  - when particular prop updates to trigger state transitions
- `render`
- `componentDidUpdate`
  - Mostly it is used to update the DOM in response to prop or state changes
- `shouldComponentUpdate`
- `componentWillUpdate`

## Unmounting

Component gets unmounted from DOM.

- `componentWillUnmount`
  - used to cancel any outgoing network requests, or remove all event listeners associated with the component
