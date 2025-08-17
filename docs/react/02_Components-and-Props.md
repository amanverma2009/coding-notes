# Components and Props

In React, **components** are the core building blocks of the UI. They allow you to split the interface into **independent, reusable pieces**.

## 1. What is a Component?

A component is a **JavaScript function** (or class) that returns a React element (JSX).

### Functional Component Example:

```jsx
function Greeting() {
  return <h1>Hello, world!</h1>;
}
````

You use it like an HTML tag:

```jsx
<Greeting />
```

## 2. Types of Components

| Type                 | Description                                      |
| -------------------- | ------------------------------------------------ |
| Functional           | Basic functions that return JSX                  |
| Class-based (legacy) | Older style with `class extends React.Component` |

Modern React uses functional components with Hooks.

## 3. Component Naming Rules

* Must start with an uppercase letter (`<MyComponent />`)
* Must return **one root element** (wrap multiple with a `<div>` or fragment)

## 4. Props (Properties)

**Props** are inputs passed into components, similar to arguments in a function.

### Passing Props:

```jsx
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}

// Usage:
<Welcome name="Alice" />
```

Using **destructuring**:

```jsx
function Welcome({ name }) {
  return <h1>Hello, {name}</h1>;
}
```

## 5. Multiple Props Example

```jsx
function Profile({ name, age }) {
  return (
    <div>
      <p>Name: {name}</p>
      <p>Age: {age}</p>
    </div>
  );
}

// Usage:
<Profile name="Bob" age={20} />
```

## 6. Default Props

You can define fallback values if a prop is not passed.

```jsx
function Button({ label = "Click Me" }) {
  return <button>{label}</button>;
}
```

Or explicitly:

```jsx
Button.defaultProps = {
  label: "Click Me"
};
```

## 7. Props Are Read-Only

Props cannot be modified inside the component. They are passed **from parent to child** and are **immutable**.

```jsx
function ChangeName({ name }) {
  name = "New Name"; // ❌ Don't do this
}
```

## 8. Children Prop

`props.children` allows you to pass elements between component tags.

```jsx
function Card({ children }) {
  return <div className="card">{children}</div>;
}

<Card>
  <h2>Title</h2>
  <p>Description inside the card.</p>
</Card>
```

## 9. Conditional Rendering with Props

```jsx
function Status({ isOnline }) {
  return <p>{isOnline ? "Online" : "Offline"}</p>;
}
```
