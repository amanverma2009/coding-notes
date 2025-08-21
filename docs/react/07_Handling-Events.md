# Handling Events

React events are similar to DOM events but use **camelCase** and work consistently across browsers. Event handlers are written as functions and passed as props.

## 1. Adding Event Handlers

```jsx
function Button() {
  function handleClick() {
    alert("Button clicked!");
  }

  return <button onClick={handleClick}>Click Me</button>;
}
```

* Use `onClick`, `onChange`, `onSubmit`, etc.
* Must be **camelCase** (`onClick` not `onclick`)

## 2. Inline Event Handler

```jsx
<button onClick={() => alert("Clicked!")}>Click Me</button>
```

Good for simple cases, but avoid complex logic inside JSX.

## 3. Passing Arguments to Event Handlers

```jsx
function Greeting({ name }) {
  function sayHello(user) {
    alert("Hello, " + user);
  }

  return <button onClick={() => sayHello(name)}>Greet</button>;
}
```

## 4. Event Object

React passes a synthetic event object automatically.

```jsx
function Input() {
  function handleChange(event) {
    console.log(event.target.value);
  }

  return <input type="text" onChange={handleChange} />;
}
```

* `event.target.value` gives input value
* Works similar to native DOM `event`

## 5. Common Events

| Event          | Usage Example               |
| -------------- | --------------------------- |
| `onClick`      | `<button onClick={fn} />`   |
| `onChange`     | `<input onChange={fn} />`   |
| `onSubmit`     | `<form onSubmit={fn} />`    |
| `onMouseEnter` | `<div onMouseEnter={fn} />` |
| `onKeyDown`    | `<input onKeyDown={fn} />`  |

## 6. Prevent Default Behavior

```jsx
function Form() {
  function handleSubmit(e) {
    e.preventDefault(); // stops page reload
    console.log("Form submitted!");
  }

  return (
    <form onSubmit={handleSubmit}>
      <button type="submit">Submit</button>
    </form>
  );
}
```

## 7. Event Binding in Loops

```jsx
const items = ["A", "B", "C"];

<ul>
  {items.map((item, i) => (
    <li key={i} onClick={() => console.log(item)}>{item}</li>
  ))}
</ul>
```

## 8. Synthetic Events

React uses **SyntheticEvent**, a wrapper for native events:

* Provides cross-browser compatibility
* Behaves like the native event object
