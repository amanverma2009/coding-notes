# Variables

CSS Variables (also called **custom properties**) allow you to store values in reusable, scoped variables using the `--` syntax.

---

## 1. Declaring a Variable

Defined inside a selector (commonly `:root` for global scope):

```css
:root {
  --main-color: #3498db;
  --padding-base: 1rem;
}
```

## 2. Using a Variable

Use the `var()` function:

```css
button {
  background-color: var(--main-color);
  padding: var(--padding-base);
}
```

## 3. Fallback Value

Use a default if the variable is undefined:

```css
p {
  color: var(--text-color, black);
}
```

## 4. Scope

Variables are **scoped** to the selector they are declared in:

```css
.container {
  --local-color: red;
}

.child {
  color: var(--local-color); /* works only if .child is inside .container */
}
```

## 5. Dynamic Theming

CSS variables can be updated dynamically (e.g. in dark mode):

```css
:root {
  --bg-color: white;
  --text-color: black;
}

.dark-mode {
  --bg-color: #121212;
  --text-color: #f0f0f0;
}

body {
  background: var(--bg-color);
  color: var(--text-color);
}
```

## 6. Inside Media Queries

Variables can be redefined based on screen size:

```css
:root {
  --font-size: 16px;
}

@media (min-width: 768px) {
  :root {
    --font-size: 18px;
  }
}

body {
  font-size: var(--font-size);
}
```

## 7. Invalid Use Cases

CSS variables **do not work** in:

* Media query expressions
* Selectors
* Keyframe names
* `@import` paths

```css
/* ❌ INVALID */
@media (min-width: var(--breakpoint)) { ... }
```
