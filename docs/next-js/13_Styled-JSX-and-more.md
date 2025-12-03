# ![ ](../assets/nextjs-logo.svg) Styled JSX in Next.js

## What is Styled JSX

Styled JSX is a built in CSS in JS solution for styling components in Next.js. It lets you write scoped CSS inside a component so the styles apply only to that component.

## Basic Usage

```jsx
export default function Button() {
  return (
    <>
      <button>Click</button>

      <style jsx>{`
        button {
          background: blue;
          color: white;
          padding: 10px 20px;
          border-radius: 6px;
        }
      `}</style>
    </>
  );
}
```

## Scoped Styling

Styles apply only to elements inside the component. They never leak outside.

## Global Styling

If you want a style to apply globally:

```jsx
<style jsx global>{`
  body {
    margin: 0;
    font-family: sans-serif;
  }
`}</style>
```

## Dynamic Styling (Using Props)

```jsx
export default function Box({ color }) {
  return (
    <>
      <div className="box" />

      <style jsx>{`
        .box {
          width: 100px;
          height: 100px;
          background: ${color};
        }
      `}</style>
    </>
  );
}
```

## Other Ways to Style in Next.js

### 1. Global CSS Files

Used for app wide styles.

Create a file like:

```
app/globals.css
```

Import in `app/layout.js`:

```jsx
import "./globals.css";
```

### 2. CSS Modules

CSS scoped to a specific component through filenames ending with `.module.css`.

Example:

```
Button.module.css
```

```css
.btn {
  background: tomato;
  padding: 10px 20px;
}
```

Use in component:

```jsx
import styles from "./Button.module.css";

export default function Button() {
  return <button className={styles.btn}>Click</button>;
}
```

### 3. Tailwind CSS

A utility first CSS framework. Very popular in Next.js projects.

Install normally then use classes:

```jsx
<button className="bg-blue-600 text-white px-4 py-2 rounded">Click</button>
```

### 4. Inline Styles

Simple quick styling.

```jsx
<div style={{ color: "red", padding: "20px" }}>Hello</div>
```

### 5. CSS in JS Libraries (Styled Components / Emotion)

These give component level styling with features like theming.

#### Styled Components Example:

```jsx
import styled from "styled-components";

const Button = styled.button`
  background: purple;
  color: white;
  padding: 10px 20px;
`;

export default function App() {
  return <Button>Click</Button>;
}
```

### 6. Sass / SCSS Support

Next.js supports `.scss` out of the box.

Example:

```
styles/main.scss
```

Import in `layout.js` or any component:

```jsx
import "./main.scss";
```

### 7. Using `classnames`

Helps conditionally apply classes with CSS Modules or global CSS.

```jsx
import cn from "classnames";
import styles from "./Box.module.css";

<div className={cn(styles.box, isActive && styles.active)} />;
```
