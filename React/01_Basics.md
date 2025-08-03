# Introduction to React

React is a **JavaScript library** for building **user interfaces**. It is maintained by Meta (formerly Facebook) and used in production by companies like Instagram, Netflix, and Airbnb.

## What is React?

- A component-based, declarative library for building UI.
- Focuses only on the **View** in MVC (Model-View-Controller).
- Uses a **virtual DOM** for fast rendering.
- Enables **reactive**, state-driven UI development.

## Key Features

| Feature           | Description |
|------------------|-------------|
| Component-Based  | Breaks UI into reusable pieces (components). |
| Declarative      | Describe **what** UI should look like based on state. |
| Virtual DOM      | Efficiently updates only what's changed. |
| JSX              | JavaScript + XML syntax for describing UI. |
| Unidirectional Data Flow | Data flows from parent to child only. |

## Why Use React?

- Faster DOM updates via virtual DOM
- Organized and reusable component structure
- Strong ecosystem (React Router, Redux, Hooks, etc.)
- Large community and long-term support
- Works with any backend or other libraries

## JSX: JavaScript + XML

JSX lets you write HTML-like code inside JavaScript.

```jsx
const element = <h1>Hello, React!</h1>;
````

This is converted to:

```js
React.createElement("h1", null, "Hello, React!");
```

## Basic Component Example

```jsx
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}

export default Welcome;
```

Usage:

```jsx
<Welcome name="Alice" />
```

## State and Props

* **Props**: Read-only data passed to a component
* **State**: Mutable data local to a component

```jsx
import { useState } from "react";

function Counter() {
  const [count, setCount] = useState(0);
  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}
```

## React Project Structure (Vite)

```bash
npm create vite@latest my-app --template react
cd my-app
npm install
npm run dev
```

Main files:

```
my-app/
├─ src/
│  ├─ App.jsx
│  ├─ main.jsx
├─ index.html
├─ package.json
```

## Common React Tools & Libraries

* **Vite / Create React App** – setup tools
* **React Router** – routing
* **Redux / Context API** – state management
* **React Query / SWR** – data fetching and caching
* **Tailwind / Styled Components** – styling
