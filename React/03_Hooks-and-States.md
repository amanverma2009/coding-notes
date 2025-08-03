# React Hooks and State

Hooks are functions that let you use React features like state and lifecycle in **functional components**.

## 1. What is State?

**State** is data that changes over time and affects what gets rendered on the screen.

### Example:

```jsx
function Counter() {
  const [count, setCount] = useState(0);
  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>+</button>
    </div>
  );
}
````

* `useState(0)` initializes `count` to 0
* `setCount()` updates it and re-renders the component

## 2. useState Hook

```js
const [state, setState] = useState(initialValue);
```

* Can hold numbers, strings, objects, arrays, etc.
* Updating state causes a re-render
* Don't mutate state directly

### Example with Object:

```jsx
const [user, setUser] = useState({ name: "Aman", age: 15 });

setUser({ ...user, age: 16 }); // use spread to keep other properties
```

## 3. Rules of Hooks

1. Only call hooks **at the top level** (not inside loops, conditions, or nested functions)
2. Only call hooks **inside React components** or **custom hooks**

## 4. Multiple useState Hooks

You can use multiple `useState` calls in one component:

```jsx
const [name, setName] = useState("");
const [email, setEmail] = useState("");
```

## 5. useEffect Hook (Intro)

`useEffect` runs code **after render**. Commonly used for:

* Fetching data
* Subscribing/unsubscribing
* DOM updates

```jsx
useEffect(() => {
  console.log("Component mounted or state changed");
}, [dependency]);
```

* Runs on mount and whenever dependencies change
* Empty dependency array `[]` = run once on mount

## 6. Derived State from Props

Avoid copying props into state unless necessary.
Instead, compute directly in JSX:

```jsx
function Greeting({ name }) {
  return <h1>Hello, {name.toUpperCase()}</h1>;
}
```

## 7. Updating State Based on Previous Value

Always use a function when new state depends on old state:

```jsx
setCount(prev => prev + 1);
```

## 8. useState with Arrays

```jsx
const [items, setItems] = useState([]);

setItems([...items, newItem]); // add item
setItems(items.filter(item => item.id !== id)); // remove item
```

## 9. Controlled Components

Inputs should be **controlled** by React state:

```jsx
const [text, setText] = useState("");

<input value={text} onChange={(e) => setText(e.target.value)} />
```

---

Hooks let you keep logic inside functional components without using classes. Start with `useState` and `useEffect` — they cover 90% of real-world cases.
