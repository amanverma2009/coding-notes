# ![ ](../assets/css-logo.svg) Display Property

The `display` property defines **how an element is rendered** in the document flow — block, inline, grid, flex, etc.

## 1. Common Display Values

### a) `block`

* Takes up the **full width**
* Starts on a **new line**

```css
div {
  display: block;
}
```

Examples: `<div>`, `<p>`, `<h1>` (default block elements)

---

### b) `inline`

* Takes up **only as much width** as needed
* Flows **inline** with text
* **Cannot** set width/height

```css
span {
  display: inline;
}
```

Examples: `<span>`, `<a>`, `<strong>` (default inline elements)

---

### c) `inline-block`

* Behaves like `inline` (flows with text)
* **Allows** width/height to be set

```css
button {
  display: inline-block;
  width: 100px;
  height: 40px;
}
```

---

### d) `none`

* **Completely hides** the element
* Removes it from layout and DOM flow

```css
p {
  display: none;
}
```

## 2. Layout Display Values

### a) `flex`

Enables **flexbox layout** for flexible, one-dimensional layouts.

```css
.container {
  display: flex;
}
```

Use with properties like `justify-content`, `align-items`, etc.

---

### b) `grid`

Enables **CSS grid layout** — two-dimensional control.

```css
.container {
  display: grid;
}
```

Use with `grid-template-columns`, `grid-gap`, etc.

---

### c) `inline-flex` / `inline-grid`

Same as `flex`/`grid`, but behaves like `inline`.

```css
span {
  display: inline-flex;
}
```

## 3. Other Values

### `table`, `table-row`, `table-cell`, etc.

Mimic HTML table behaviors.

```css
div {
  display: table;
}
```

## 4. Default Values by Tag

| Tag       | Default `display` |
| --------- | ----------------- |
| `<div>`   | `block`           |
| `<span>`  | `inline`          |
| `<img>`   | `inline-block`    |
| `<table>` | `table`           |

## 5. Visual Summary

| Display        | New Line | Width/Height Allowed | Layout Control |
| -------------- | -------- | -------------------- | -------------- |
| `block`        | ✅        | ✅                    | ❌              |
| `inline`       | ❌        | ❌                    | ❌              |
| `inline-block` | ❌        | ✅                    | ❌              |
| `flex`         | ✅        | ✅                    | ✅ (1D)         |
| `grid`         | ✅        | ✅                    | ✅ (2D)         |
