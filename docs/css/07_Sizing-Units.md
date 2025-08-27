# ![ ](../assets/css-logo.svg) Sizing Units

CSS sizing units define dimensions like `width`, `height`, `padding`, `margin`, and `font-size`. They fall into two main categories: **absolute** and **relative** units.

## 1. Absolute Units

These do **not** scale with screen size or context — they remain fixed.

| Unit | Name         | Description                      |
|------|--------------|----------------------------------|
| `px` | Pixels       | Most commonly used; screen-relative |
| `pt` | Points       | 1pt = 1/72 inch (used in print)  |
| `cm` | Centimeters  | Physical measurement             |
| `mm` | Millimeters  | Physical measurement             |
| `in` | Inches       | 1in = 96px (standard)            |

### Example:

```css
.box {
  width: 200px;
  font-size: 12pt;
}
```

**Use when:** you want precise control (e.g. fixed UI components), but avoid for responsive designs.

## 2. Relative Units

These scale based on **parent elements**, **root**, or **viewport**.

### a) `%` — Percentage

Relative to the **parent** element's size.

```css
div {
  width: 50%; /* 50% of parent */
}
```

---

### b) `em` — Relative to Parent Font Size

1 `em` = font-size of the current element’s **parent**.

```css
/* If parent has 16px font size */
p {
  font-size: 2em; /* 32px */
}
```

Stacking ems can cause unintended scaling (compound effect).

---

### c) `rem` — Relative to Root Element

1 `rem` = font-size of the `html` element.

```css
html {
  font-size: 16px;
}

h1 {
  font-size: 2rem; /* 32px */
}
```

**Preferred over `em`** for consistent, predictable sizing.

---

### d) `vw`, `vh`, `vmin`, `vmax` — Viewport Units

| Unit   | Description                                      |
|--------|--------------------------------------------------|
| `vw`   | 1% of viewport **width**                         |
| `vh`   | 1% of viewport **height**                        |
| `vmin` | 1% of **smaller** of `vw` or `vh`                |
| `vmax` | 1% of **larger** of `vw` or `vh`                 |

```css
section {
  width: 100vw;
  height: 100vh;
}

.hero-text {
  font-size: 5vmin;
}
```

Great for full-screen layouts and responsive typography.

## 3. `calc()` — Dynamic Calculations

Combines units for flexible sizing.

```css
.container {
  width: calc(100% - 60px);
  height: calc(50vh + 100px);
}
```

Useful for subtracting fixed elements like headers or sidebars.

## Best Practices

- Use `rem` for **font sizes** (scales with user settings).
- Use `px` or `%` for **borders, paddings**, depending on layout needs.
- Use `vw`, `vh` for **responsive layouts**.
- Avoid absolute units like `cm`, `pt` in screen designs.

---
