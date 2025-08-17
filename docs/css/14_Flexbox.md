# Flexbox

**Flexbox** (Flexible Box Layout) is a 1-dimensional layout system that makes it easy to align, distribute, and order space among items in a container — either horizontally or vertically.

---

## 1. Enabling Flex

```css
.container {
  display: flex;
}
```

This makes all **direct children** flex items.

## 2. Main vs Cross Axis

* **Main Axis**: Defined by `flex-direction`
* **Cross Axis**: Perpendicular to the main axis

| `flex-direction` value | Main Axis  | Cross Axis |
| ---------------------- | ---------- | ---------- |
| `row` (default)        | horizontal | vertical   |
| `column`               | vertical   | horizontal |

## 3. `flex-direction`

```css
.container {
  flex-direction: row | row-reverse | column | column-reverse;
}
```

## 4. `justify-content` (Main Axis)

Aligns items along the **main axis**.

```css
.container {
  justify-content: flex-start | flex-end | center | space-between | space-around | space-evenly;
}
```

## 5. `align-items` (Cross Axis)

Aligns items along the **cross axis**.

```css
.container {
  align-items: flex-start | flex-end | center | stretch | baseline;
}
```

## 6. `align-content` (Cross Axis, multiple rows)

Used when there are **multiple lines** (wrapping).

```css
.container {
  align-content: flex-start | center | space-between;
}
```

## 7. `flex-wrap`

Controls whether items wrap to the next line.

```css
.container {
  flex-wrap: nowrap | wrap | wrap-reverse;
}
```

## 8. Shorthand: `flex-flow`

Combines `flex-direction` + `flex-wrap`

```css
.container {
  flex-flow: row wrap;
}
```

## 9. Flex Item Properties

### a) `order`

Controls item **visual order**.

```css
.item {
  order: 2; /* Default is 0 */
}
```

### b) `flex-grow`

Defines how much the item **expands** relative to others.

```css
.item {
  flex-grow: 1;
}
```

### c) `flex-shrink`

Defines how much the item **shrinks**.

```css
.item {
  flex-shrink: 0;
}
```

### d) `flex-basis`

Sets the **initial size** before growing/shrinking.

```css
.item {
  flex-basis: 200px;
}
```

### e) Shorthand: `flex`

```css
.item {
  flex: 1 1 200px; /* grow shrink basis */
}
```

## 10. `align-self`

Overrides `align-items` **for a single item**.

```css
.item {
  align-self: center;
}
```

## Example Layout

```css
.container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
```

```html
<div class="container">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>
```
