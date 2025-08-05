# Conditional Rendering and Rendering Lists in React

React lets you render components or elements **dynamically** based on conditions or data arrays. This is done using JavaScript logic inside JSX.

## 1. Conditional Rendering

You can conditionally show UI using `if`, `ternary`, `&&`, or conditional functions.

### a. Using if-else (outside JSX)

```jsx
function Message({ isLoggedIn }) {
  if (isLoggedIn) {
    return <h1>Welcome back!</h1>;
  } else {
    return <h1>Please sign in.</h1>;
  }
}
````

### b. Ternary Operator

```jsx
<p>{isDarkMode ? "Dark Mode" : "Light Mode"}</p>
```

### c. Logical AND (`&&`)

```jsx
{isAdmin && <button>Delete</button>}
```

Only renders `<button>` if `isAdmin` is true.

## 2. Prevent Rendering

Return `null` to render nothing:

```jsx
if (!user) return null;
```

## 3. Rendering Lists

Use `Array.map()` to render elements from data:

```jsx
const users = ["Alice", "Bob", "Charlie"];

<ul>
  {users.map((name, index) => (
    <li key={index}>{name}</li>
  ))}
</ul>
```

* Wrap with a container (`<ul>` or `<div>`)
* Use a **unique `key`** prop for each item

## 4. Rendering List of Objects

```jsx
const todos = [
  { id: 1, task: "Read" },
  { id: 2, task: "Write" }
];

<ul>
  {todos.map(todo => (
    <li key={todo.id}>{todo.task}</li>
  ))}
</ul>
```

## 5. Conditional Rendering Inside Map

```jsx
{todos.map(todo => (
  <li key={todo.id}>
    {todo.completed ? <s>{todo.task}</s> : todo.task}
  </li>
))}
```

## 6. Key Prop (Important)

* Must be **unique** and **stable**
* Never use `index` as `key` if list can change
* Keys help React track what changed efficiently
