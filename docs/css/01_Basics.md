# Basics

CSS (**Cascading Style Sheets**) is used to **style** HTML elements — controlling their layout, color, spacing, fonts, and more.

## 1. CSS Syntax

```css
selector {
  property: value;
}
```

### Example:

```css
p {
  color: blue;
  font-size: 16px;
}
```

### Output:

<pre>
p {
  color: blue;
  font-size: 16px;
}
</pre>

## 2. Adding CSS to HTML

There are **3 ways** to apply CSS:

### a) Inline CSS

```html
<p style="color: red;">Inline styled paragraph</p>
```

### b) Internal CSS (within `<style>` tag)

```html
<head>
  <style>
    h1 {
      text-align: center;
      color: green;
    }
  </style>
</head>
```

### c) External CSS (best practice)

Inside `<head>` in `index.html`

```html
<link rel="stylesheet" href="styles.css">
```

And in `styles.css`:

```css
body {
  background-color: #f0f0f0;
}
```

## 3. Comments in CSS

```css
/* This is a CSS comment */
```

## 4. Colors in CSS

You can use:

* **Named colors** (`red`, `blue`, `green`)
* **Hex codes** (`#ff0000`)
* **RGB** (`rgb(255, 0, 0)`)
* **HSL** (`hsl(0, 100%, 50%)`)

```css
body {
  background-color: #121212;
  color: rgb(255, 255, 255);
}
```

## 5. Inheritance & Specificity

* Some CSS properties (like `color`, `font-family`) are **inherited** by default
* **Specificity** decides which rule wins if multiple styles apply
* Inline > ID > Class > Element selector

```html
<style>
  #heading { color: red; }
  .title { color: blue; }
  h1 { color: green; }
</style>

<h1 id="heading" class="title">Hello</h1>
```

**Output color:** Red (`#heading` wins)

## 6. Box Model

Every HTML element is a box made of:

```css
+-----------------------------+
|        Margin               |
|   +---------------------+   |
|   |     Border          |   |
|   |  +-------------+    |   |
|   |  |  Padding    |    |   |
|   |  | +--------+  |    |   |
|   |  | | Content|  |    |   |
|   |  | +--------+  |    |   |
|   |  +-------------+    |   |
|   +---------------------+   |
+-----------------------------+
```
