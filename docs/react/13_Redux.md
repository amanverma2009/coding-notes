# Redux

## What is Redux?

Redux is a **state management library** for JavaScript applications, often used with React but can also be used with Angular, Vue, or plain JS.
It helps manage the **state of an application in a predictable way** using a single source of truth (the store).

## Why Use Redux?

- **Centralized State Management**: All application state is stored in one place (the store).
- **Predictable State Changes**: State can only be changed through specific functions (reducers) triggered by actions.
- **Easier Debugging**: Redux provides tools to track every state change (Redux DevTools).
- **Consistency Across Components**: Different components can easily access and update the same state.
- **Improved Maintainability**: Clear flow of data and separation of concerns.

## Redux Core Concepts

### 1. Store

- The **store** is a JavaScript object that holds the entire state tree of your application.
- There is only **one store** in a Redux application.

```js
import { createStore } from "redux";
const store = createStore(reducer);
```

### 2. Actions

- Actions are plain JavaScript **objects** that describe **what happened**.
- Each action has a **type** (a string constant) and optionally some **payload** (data).

```js
const incrementAction = {
  type: "INCREMENT",
};

const addTodoAction = {
  type: "ADD_TODO",
  payload: "Learn Redux",
};
```

### 3. Reducers

- Reducers are **pure functions** that specify how the state changes in response to actions.
- They take the **current state** and an **action** as arguments and return a **new state**.

```js
function counterReducer(state = { count: 0 }, action) {
  switch (action.type) {
    case "INCREMENT":
      return { count: state.count + 1 };
    case "DECREMENT":
      return { count: state.count - 1 };
    default:
      return state;
  }
}
```

### 4. Dispatch

- The `dispatch()` function sends an action to the Redux store.
- When an action is dispatched, the store runs the reducer to update the state.

```js
store.dispatch({ type: "INCREMENT" });
```

### 5. Subscribe

- The `subscribe()` method allows you to listen for state changes in the store.

```js
store.subscribe(() => {
  console.log(store.getState());
});
```

## Redux Data Flow (Unidirectional)

1. **Dispatch an Action** – Trigger an event that describes what happened.
2. **Reducer** – Receives the action and current state, returns a new state.
3. **Store** – Updates the state based on the reducer’s output.
4. **UI** – Re-renders based on the updated state.

**Flow Diagram:**

```text
UI → Action → Reducer → Store → UI
```

## Example: Simple Counter

```js
import { createStore } from "redux";

// Reducer
function counterReducer(state = { count: 0 }, action) {
  switch (action.type) {
    case "INCREMENT":
      return { count: state.count + 1 };
    case "DECREMENT":
      return { count: state.count - 1 };
    default:
      return state;
  }
}

// Create store
const store = createStore(counterReducer);

// Subscribe
store.subscribe(() => console.log(store.getState()));

// Dispatch actions
store.dispatch({ type: "INCREMENT" }); // {count: 1}
store.dispatch({ type: "INCREMENT" }); // {count: 2}
store.dispatch({ type: "DECREMENT" }); // {count: 1}
```

## Using Redux with React

### Install:

```bash
npm install redux react-redux
```

### Provider Setup

Wrap your app with the Redux Provider to give components access to the store.

```js
import React from "react";
import ReactDOM from "react-dom";
import { Provider } from "react-redux";
import { createStore } from "redux";
import App from "./App";
import counterReducer from "./counterReducer";

const store = createStore(counterReducer);

ReactDOM.render(
  <Provider store={store}>
    <App />
  </Provider>,
  document.getElementById("root")
);
```

### Accessing State and Dispatch in Components

#### `useSelector` – to get state

#### `useDispatch` – to send actions

```js
import React from "react";
import { useSelector, useDispatch } from "react-redux";

function Counter() {
  const count = useSelector((state) => state.count);
  const dispatch = useDispatch();

  return (
    <div>
      <h1>{count}</h1>
      <button onClick={() => dispatch({ type: "INCREMENT" })}>+</button>
      <button onClick={() => dispatch({ type: "DECREMENT" })}>-</button>
    </div>
  );
}

export default Counter;
```

## Redux Toolkit (RTK)

Redux Toolkit simplifies Redux with less boilerplate.

### Install:

```bash
npm install @reduxjs/toolkit react-redux
```

### Create a Slice

```js
import { createSlice, configureStore } from "@reduxjs/toolkit";

const counterSlice = createSlice({
  name: "counter",
  initialState: { count: 0 },
  reducers: {
    increment: (state) => {
      state.count += 1;
    },
    decrement: (state) => {
      state.count -= 1;
    },
  },
});

export const { increment, decrement } = counterSlice.actions;
const store = configureStore({ reducer: counterSlice.reducer });
export default store;
```

### Use in Component

```js
import { useSelector, useDispatch } from "react-redux";
import { increment, decrement } from "./store";

function Counter() {
  const count = useSelector((state) => state.count);
  const dispatch = useDispatch();

  return (
    <>
      <h1>{count}</h1>
      <button onClick={() => dispatch(increment())}>+</button>
      <button onClick={() => dispatch(decrement())}>-</button>
    </>
  );
}
```

## Middleware in Redux

Middleware allows handling of **side effects** (like async API calls).

### Common Middleware:

- **redux-thunk**: For asynchronous actions.
- **redux-saga**: For complex side effects and background tasks.

### Example (redux-thunk):

```bash
npm install redux-thunk
```

```js
import { createStore, applyMiddleware } from "redux";
import thunk from "redux-thunk";

const store = createStore(reducer, applyMiddleware(thunk));

const fetchData = () => {
  return async (dispatch) => {
    const response = await fetch("https://api.example.com/data");
    const data = await response.json();
    dispatch({ type: "DATA_LOADED", payload: data });
  };
};
```

## Redux DevTools

- A browser extension that lets you inspect actions, state, and changes.
- Install it and enable it in your store setup:

```js
const store = createStore(
  reducer,
  window.__REDUX_DEVTOOLS_EXTENSION__ && window.__REDUX_DEVTOOLS_EXTENSION__()
);
```

## Advantages of Redux

- Predictable state changes
- Easy debugging and testing
- Works well with any UI layer (not limited to React)
- Centralized and consistent data handling

## Disadvantages of Redux

- Boilerplate code (reduced by Redux Toolkit)
- Complex setup for small projects
- Learning curve for beginners

## When to Use Redux

Use Redux when:

- You have **complex state logic** shared across many components.
- Multiple components need access to the same data.
- You want **predictable and trackable state changes**.

Avoid Redux when:

- The app is small and simple.
- State can be handled easily using React’s `useState` or `useContext`.
