# ![ ](../assets/react_light.svg#only-light) ![ ](../assets/react_dark.svg#only-dark) useContext Hook

The `useContext` hook provides a way to share state and values across the component tree **without passing props manually** at every level.

## 1. Creating a Context

```jsx
import { createContext } from "react";

const ThemeContext = createContext("light"); // default value
export default ThemeContext;
```

## 2. Providing Context

Wrap components with the `Provider` to pass data down.

```jsx
import ThemeContext from "./ThemeContext";

function App() {
  return (
    <ThemeContext.Provider value="dark">
      <Toolbar />
    </ThemeContext.Provider>
  );
}
```

## 3. Consuming Context with useContext

```jsx
import { useContext } from "react";
import ThemeContext from "./ThemeContext";

function Button() {
  const theme = useContext(ThemeContext);
  return <button className={theme}>Click Me</button>;
}
```

* No need for `props`
* Any component inside the `Provider` can access the value

## 4. Nested Providers

You can use multiple contexts:

```jsx
<UserContext.Provider value={{ name: "Alice" }}>
  <ThemeContext.Provider value="dark">
    <Dashboard />
  </ThemeContext.Provider>
</UserContext.Provider>
```

Each component can consume one or both contexts.

## 5. Updating Context

Pass state as a value:

```jsx
function App() {
  const [theme, setTheme] = useState("light");

  return (
    <ThemeContext.Provider value={{ theme, setTheme }}>
      <Toolbar />
    </ThemeContext.Provider>
  );
}
```

Consume and update:

```jsx
function ThemeToggle() {
  const { theme, setTheme } = useContext(ThemeContext);

  return (
    <button onClick={() => setTheme(theme === "light" ? "dark" : "light")}>
      Switch Theme
    </button>
  );
}
```

## 6. When to Use useContext

* Global theme (dark/light)
* User authentication data
* Current language/locale
* Global settings or configurations

Avoid overusing context for everything — prefer props for local state.
