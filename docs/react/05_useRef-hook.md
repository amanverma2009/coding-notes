# useRef Hook

The `useRef` hook gives you a **mutable reference** to a DOM element or any value that persists across renders without causing re-renders.

## 1. Syntax

```jsx
const ref = useRef(initialValue);
````

* `ref.current` holds the value
* Unlike state, updating `ref.current` **doesn’t re-render** the component

## 2. Accessing DOM Elements

```jsx
import { useRef, useEffect } from "react";

function InputFocus() {
  const inputRef = useRef(null);

  useEffect(() => {
    inputRef.current.focus(); // focus input on mount
  }, []);

  return <input ref={inputRef} type="text" />;
}
```

* The `ref` is attached to the JSX element
* After mounting, `ref.current` points to the DOM node

## 3. Persisting Values Without Re-Renders

```jsx
function Timer() {
  const count = useRef(0);

  useEffect(() => {
    const interval = setInterval(() => {
      count.current += 1;
      console.log(count.current);
    }, 1000);
    return () => clearInterval(interval);
  }, []);
}
```

* `count` is preserved between renders
* Changes to `count.current` do **not** trigger a re-render

## 4. useRef vs useState

| Feature          | `useRef`                          | `useState`               |
| ---------------- | --------------------------------- | ------------------------ |
| Causes re-render | ❌ No                              | ✅ Yes                    |
| Stores value     | ✅ Yes                             | ✅ Yes                    |
| DOM access       | ✅ Yes (`ref.current`)             | ❌ No                     |
| Use case         | DOM refs, timers, persistent vars | UI state / reactive data |

## 5. useRef in Event Handlers

Good for holding previous values or timers:

```jsx
const intervalRef = useRef(null);

function stopTimer() {
  clearInterval(intervalRef.current);
}
```

## 6. Forwarding Refs (Advanced)

To pass a ref to a child component:

```jsx
const Input = React.forwardRef((props, ref) => {
  return <input ref={ref} {...props} />;
});
```
