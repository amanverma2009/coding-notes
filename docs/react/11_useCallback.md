# ![ ](../assets/react_light.svg#only-light) ![ ](../assets/react_dark.svg#only-dark) useCallback Hook

The `useCallback` hook returns a **memoized version of a callback function** that only changes when its dependencies change.  
It is mainly used to **prevent unnecessary re-renders** of child components that receive functions as props.

## 1. Syntax

```jsx
const memoizedCallback = useCallback(() => {
  // function body
}, [dependencies]);
```

* First argument → function to memoize
* Second argument → dependency array
* Returns the **same function reference** unless dependencies change

## 2. Example Without useCallback (Problem)

```jsx
function Parent() {
  const [count, setCount] = useState(0);

  const increment = () => setCount(c => c + 1);

  return <Child onIncrement={increment} />;
}

function Child({ onIncrement }) {
  console.log("Child rendered");
  return <button onClick={onIncrement}>+</button>;
}
```

Even if unrelated state changes, `increment` is recreated, causing `Child` to re-render.

## 3. Fix with useCallback

```jsx
function Parent() {
  const [count, setCount] = useState(0);

  const increment = useCallback(() => {
    setCount(c => c + 1);
  }, []);

  return <Child onIncrement={increment} />;
}
```

Now, `increment` keeps the same reference across renders → `Child` won’t re-render unnecessarily.

## 4. useCallback with Dependencies

```jsx
const handleSearch = useCallback(() => {
  console.log("Searching:", query);
}, [query]);
```

* The function changes only when `query` changes
* Prevents re-creating function on unrelated updates

## 5. useCallback with React.memo

Often combined with `React.memo` for optimization:

```jsx
const Child = React.memo(function Child({ onClick }) {
  console.log("Child rendered");
  return <button onClick={onClick}>Click</button>;
});
```

* `React.memo` prevents re-render if props don’t change
* `useCallback` ensures the function prop doesn’t change unnecessarily

## 6. useCallback vs useMemo

| Hook          | Purpose                 |
| ------------- | ----------------------- |
| `useMemo`     | Memoizes a **value**    |
| `useCallback` | Memoizes a **function** |

Example:

```jsx
const value = useMemo(() => expensiveCalc(a), [a]);
const fn = useCallback(() => doSomething(a), [a]);
```

## 7. When to Use

* When passing functions as props to memoized child components
* Preventing re-renders caused by changing function references
* Optimizing lists with callbacks (e.g., `onClick`, `onChange`)

Avoid overusing — only apply when child components re-render unnecessarily.
