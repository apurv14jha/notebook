# React Questions

### What are reducers?

- Reducers are pure functions that take the previous state and an action to return a new state.

## Redux

### What is Redux?

- Redux is a state management library for React that helps manage global state by providing a single source of truth for state data, making it easier to manage complex applications with multiple components and interactions.

### Why is Redux needed?

- Redux provides a **predictable way to handle data flow**, preventing inconsistencies and making it easier to debug and test.
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

### What is the general Redux workflow?

- Redux Workflow:
  1. Define state and reducers with createSlice.
  2. createSlice generates action creators and types.
  3. Write reducer logic to handle actions and update state.
  4. Create store with configureStore.
  5. Components dispatch actions using dispatch.
  6. Reducers update state, triggering re-renders.
  7. Components access updated state via useSelector.

### What is the store in Redux?

- The Redux store is a centralized container that holds the entire application's state.
- In other words, it's like a single, shared memory bank where all the data your app needs is stored and managed.

### How do you create a Redux store?

- We create a new Redux store using the configureStore function.
- We use it like this:

  ```javascript
  // file name: src/app/store.js
  import { configureStore } from "@reduxjs/toolkit";

  export default configureStore({
    reducer: {},
  });
  ```

### What do you do when you have created an empty Redux store?

- We wrap our app in a \<Provider\> component in the main entry point file (usually index.js) and pass the Redux store as a prop to make it available to all React components.
- Here's how we can do that:

  ```javascript
  // file name: src/index.js
  import React from "react";
  import ReactDOM from "react-dom/client";
  import "./index.css";
  import App from "./App";
  import store from "./app/store";
  import { Provider } from "react-redux";

  const root = ReactDOM.createRoot(document.getElementById("root"));

  root.render(
    <Provider store={store}>
      <App />
    </Provider>
  );
  ```

### What are Actions in Redux?

- Actions are messages sent to the store to trigger state changes.
- In other words, actions are like requests telling the store to do something.

### What is Slice in Redux?

- A slice in Redux is a self-contained piece of state that represents a specific domain or feature of the application.
- In other words, a slice is a way to organize and manage different parts of your application’s state separately.

### How do you create a slice in Redux?

- We can create a slice using the createSlice function to automatically generate action creators and action types based on the reducers (functions that define how the state changes) we define.
- Here's how we can do that:

```javascript
// file name: src/features/counter/counterSlice.js
import { createSlice } from "@reduxjs/toolkit";

const initialState = {
  value: 0,
};

const counterSlice = createSlice({
  name: "counter",
  initialState,
  reducers: {
    increment: (state) => {
      state.value += 1;
    },
    decrement: (state) => {
      state.value -= 1;
    },
    incrementByAmount: (state, action) => {
      state.value += action.payload;
    },
  },
});

export const { increment, decrement, incrementByAmount } = counterSlice.actions;
export default counterSlice.reducer;
```

### What are Reducers in Redux?

- Reducers are pure functions that determine how the state changes based on the received action.
- In other words, reducers are the rules that decide how to update the store's data based on the requests (actions).

### Can you give an example of a reducer?

- Here's an example of a reducer in Redux:

````javascript
  increment: (state) => {
    state.value += 1;
  }
```

### What is middleware in Redux?

- Middleware is software that sits between the action and the reducer, allowing for custom logic before state updates.
- In other words, it's like a gatekeeper that examines and can modify actions before they reach the store.

````

```

```
