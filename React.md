# React Questions

### What are reducers?

- Reducers are pure functions that take the previous state and an action to return a new state.

## Redux

### What is Redux?

- Redux is a state management library for React that helps manage global state by providing a single source of truth for state data, making it easier to manage complex applications with multiple components and interactions.

### Why is Redux needed?

- Redux is essential for managing complex application state, especially in large-scale React projects.
- It provides a **predictable way to handle data flow**, preventing inconsistencies and making it easier to debug and test.
- By centralizing state, Redux simplifies **data sharing between components**, improving code organization and maintainability.

### What is Redux Toolkit?

- Redux Toolkit is an official, opinionated set of tools that simplifies Redux development.
- It includes utilities for configuring stores, creating reducers, managing asynchronous logic, and more.

### Why does Redux recommend Redux Toolkit as the preferred way to use Redux?

- Redux recommends Redux Toolkit as the preferred way to use Redux because it:
  1.  significantly reduces boilerplate code
  2.  enforces best practices
  3.  provides a more enjoyable development experience.
  4.  incorporates essential features like middleware and immutability helpers

### What are the components of Redux?

- Redux consists of Store, Actions, Reducers and Middleware.

### What is the Redux workflow?

1.  **State definition:** Define the initial state and reducers using createSlice.
2.  **Action creation:** _createSlice_ automatically generates action creators and action types.
3.  **Reducer logic:** Write reducer functions within createSlice to handle actions and update the state.
4.  **Store creation:** Use _configureStore_ to create the Redux store, which can include multiple slices.
5.  **Dispatching actions:** Components dispatch actions using the _dispatch_ function.
6.  **State updates:** Reducers process dispatched actions and return the new state.
7.  **Re-rendering:** Components re-render based on the updated state from the store, typically accessed via _useSelector_.
