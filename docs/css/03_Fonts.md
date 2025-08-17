# CSS Fonts

Fonts control the **appearance of text** — including typeface, size, weight, spacing, and more.

## 1. Font Family

Set the typeface using `font-family`. Always include a fallback.

```css
body {
  font-family: 'Arial', 'Helvetica', sans-serif;
}
```

## 2. Font Size

Controls the size of the text.

```css
p {
  font-size: 16px;
}
```

### Common units:

* `px` — absolute (pixels)
* `em` — relative to parent
* `rem` — relative to root (`html`)
* `%` — relative to parent

```css
h1 {
  font-size: 2em;  /* 2x the parent size */
}
```

## 3. Font Weight

Controls thickness of text.

```css
strong {
  font-weight: bold; /* or numeric: 100 to 900 */
}
```

## 4. Font Style

Used for italics and oblique styles.

```css
em {
  font-style: italic;
}
```

## 5. Font Variant

Used for small-caps.

```css
p {
  font-variant: small-caps;
}
```

## 6. Line Height

Controls vertical spacing between lines of text.

```css
p {
  line-height: 1.6;
}
```

## 7. Shorthand Property

Combine multiple font properties.

```css
p {
  font: italic small-caps bold 16px/1.5 'Georgia', serif;
}
```

## 8. Web Fonts

Import custom fonts using `@font-face` or via Google Fonts:

### Example (Google Fonts):

```html
<link href="https://fonts.googleapis.com/css2?family=Roboto&display=swap" rel="stylesheet">
```

```css
body {
  font-family: 'Roboto', sans-serif;
}
```
