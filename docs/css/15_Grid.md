# Grid

**Grid** is a 2-dimensional layout system for arranging items in rows and columns.

## 1. Enabling Grid

```css
.container {
  display: grid;
}
```

All direct children become grid items.

## 2. Defining Columns and Rows

```css
.container {
  grid-template-columns: 200px 1fr 2fr;
  grid-template-rows: 100px auto;
}
```

* `px` = fixed size
* `fr` = fraction of remaining space
* `auto` = size based on content

## 3. Repeat Notation

```css
grid-template-columns: repeat(3, 1fr);
```

Same as: `1fr 1fr 1fr`

## 4. Gap Between Items

```css
.container {
  gap: 20px; /* row + column gap */
}
```

Split version:

```css
row-gap: 10px;
column-gap: 15px;
```

## 5. Placing Items

```css
.item {
  grid-column: 1 / 3; /* spans columns 1 and 2 */
  grid-row: 2 / 4;
}
```

Or shorthand:

```css
grid-area: row-start / column-start / row-end / column-end;
```

## 6. Named Areas

```css
.container {
  grid-template-areas:
    "header header"
    "sidebar main"
    "footer footer";
}

.header {
  grid-area: header;
}
```

## 7. Implicit Tracks

Grid auto-generates rows/columns if needed.

```css
.container {
  grid-auto-rows: 100px;
}
```

## 8. Auto-Placement

Items are placed in the next available cell by default.

```css
.container {
  grid-auto-flow: row | column | dense;
}
```

## 9. Responsive Grid

```css
.container {
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
}
```

This makes columns responsive and wrap when space is tight.

## 10. Aligning Content

* Align grid items:

```css
justify-items: start | center | end | stretch;
align-items: start | center | end | stretch;
```

* Align the grid as a whole:

```css
justify-content: center | space-between | space-around;
align-content: center;
```
