# ![ ](../assets/css-logo.svg) Position

The `position` property defines how an element is placed in the document — static, relative, absolute, fixed, or sticky.

## 1. `static` (default)

* Normal document flow
* `top`, `left`, `right`, `bottom` have **no effect**

```css
div {
  position: static;
}
```

## 2. `relative`

* Positioned **relative to its normal position**
* Leaves original space in the flow

```css
.box {
  position: relative;
  top: 10px;
  left: 20px;
}
```

Used to **nudge** elements or create a reference for absolutely positioned children.

## 3. `absolute`

* Removed from document flow
* Positioned **relative to the nearest positioned ancestor**
* If none, it uses the `html` (viewport)

```css
.child {
  position: absolute;
  top: 0;
  right: 0;
}
```

**Requires parent** to be `relative`, `absolute`, or `fixed` if you want local positioning.

## 4. `fixed`

* Removed from flow
* Positioned **relative to the viewport**
* **Stays in place** when scrolling

```css
.header {
  position: fixed;
  top: 0;
  width: 100%;
}
```

Used for navbars, back-to-top buttons, etc.

## 5. `sticky`

* Acts like `relative` until a threshold is reached, then becomes `fixed`
* Requires a **top/left/right/bottom** value

```css
.menu {
  position: sticky;
  top: 0;
}
```

**Parent must have height** for sticky to work properly.

## 6. Z-Index

Use `z-index` to control **stacking order** (higher = on top).

```css
.box {
  position: absolute;
  z-index: 10;
}
```

Only works on **positioned** elements (not `static`).

## Summary Table

| Position   | In Flow | Offset Allowed | Scrolls with Page | Reference Point             |
| ---------- | ------- | -------------- | ----------------- | --------------------------- |
| `static`   | ✅       | ❌              | ✅                 | Normal document flow        |
| `relative` | ✅       | ✅              | ✅                 | Own original position       |
| `absolute` | ❌       | ✅              | ❌                 | Nearest positioned ancestor |
| `fixed`    | ❌       | ✅              | ❌                 | Viewport                    |
| `sticky`   | ✅/❌     | ✅              | ✅/❌               | Toggles: self → viewport    |
