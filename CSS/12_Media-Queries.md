# CSS Media Queries

Media queries let you apply CSS **based on screen/device properties**, enabling **responsive design**.

## 1. Basic Syntax

```css
@media media-type and (condition) {
  /* CSS rules */
}
```

Example:

```css
@media screen and (max-width: 768px) {
  body {
    font-size: 14px;
  }
}
```

## 2. Media Types

| Type     | Description                     |
| -------- | ------------------------------- |
| `all`    | Default, applies to all devices |
| `screen` | Computer screens, tablets, etc. |
| `print`  | Print previews and printers     |
| `speech` | Screen readers                  |

## 3. Common Features (Conditions)

| Feature                | Example                 | Description                 |
| ---------------------- | ----------------------- | --------------------------- |
| `max-width`            | `max-width: 600px`      | Target screens **≤** 600px  |
| `min-width`            | `min-width: 1024px`     | Target screens **≥** 1024px |
| `max-height`           | `max-height: 500px`     | Target short screens        |
| `orientation`          | `orientation: portrait` | Portrait vs. landscape      |
| `prefers-color-scheme` | `dark`/`light`          | Light/dark mode detection   |

## 4. Responsive Breakpoints (Example)

```css
/* Mobile first */
body {
  font-size: 14px;
}

@media (min-width: 600px) {
  body {
    font-size: 16px;
  }
}

@media (min-width: 1024px) {
  body {
    font-size: 18px;
  }
}
```

## 5. Multiple Conditions

```css
@media (min-width: 600px) and (max-width: 1024px) {
  .box {
    background: yellow;
  }
}
```

Use `,` for OR conditions:

```css
@media (max-width: 500px), (min-width: 1200px) {
  .header {
    display: none;
  }
}
```

## 6. Dark Mode Example

```css
@media (prefers-color-scheme: dark) {
  body {
    background: #121212;
    color: #f0f0f0;
  }
}
```

## 7. Print Styles

```css
@media print {
  nav, footer {
    display: none;
  }

  body {
    font-size: 12pt;
  }
}
```
