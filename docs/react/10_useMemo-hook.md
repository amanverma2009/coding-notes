# React useMemo Hook

The `useMemo` hook is used to **memoize expensive calculations** so they are not re-executed on every render unless their dependencies change.

## 1. Syntax

```jsx
const memoizedValue = useMemo(() => computeValue(a, b), [a, b]);
```

* First argument → function that returns a value
* Second argument → dependency array
* Recomputes only when dependencies change

## 2. Example: Expensive Calculation

```jsx
import { useMemo, useState } from "react";

function Factorial() {
  const [num, setNum] = useState(5);
  const [theme, setTheme] = useState("light");

  const factorial = useMemo(() => {
    function calcFactorial(n) {
      console.log("Calculating...");
      return n <= 0 ? 1 : n * calcFactorial(n - 1);
    }
    return calcFactorial(num);
  }, [num]);

  return (
    <div className={theme}>
      <p>Factorial of {num} is {factorial}</p>
      <button onClick={() => setNum(num + 1)}>Increase</button>
      <button onClick={() => setTheme(theme === "light" ? "dark" : "light")}>Toggle Theme</button>
    </div>
  );
}
```

* Changing `theme` won’t trigger recalculation of factorial
* Calculation only runs when `num` changes

## 3. Without useMemo (Problem)

```jsx
const factorial = calcFactorial(num); // recalculated every render
```

Even if only unrelated state changes, the function runs again → performance issue.

## 4. Memoizing Derived Data

```jsx
const sortedItems = useMemo(() => {
  return items.sort((a, b) => a.localeCompare(b));
}, [items]);
```

Prevents unnecessary sorting when `items` hasn’t changed.

## 5. useMemo vs useCallback

* **useMemo** → memoizes a **value**
* **useCallback** → memoizes a **function**

Example:

```jsx
const value = useMemo(() => expensiveCalc(a), [a]);
const callback = useCallback(() => doSomething(a), [a]);
```

## 6. When to Use

* Expensive calculations (sorting, filtering, large loops)
* Preventing unnecessary re-renders of child components
* Memoizing derived state

Avoid using it everywhere — use only when performance issues appear.
