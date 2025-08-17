# CSS Overflow

The `overflow` property controls what happens when content **exceeds** the size of its container.


## 1. Values

### a) `visible` (default)

Content **spills out** of the box — no clipping.

```css
.box {
  overflow: visible;
}
```

---

### b) `hidden`

Extra content is **cut off** and not visible.

```css
.box {
  overflow: hidden;
}
```

Used when you want a clean container without scroll.

---

### c) `scroll`

Adds **scrollbars** (always visible), regardless of need.

```css
.box {
  overflow: scroll;
}
```

**Bad UX** if scrolling isn’t needed — use `auto` instead.

---

### d) `auto`

Adds scrollbars **only if** needed.

```css
.box {
  overflow: auto;
}
```

Best for responsive and accessible designs.

## 2. Overflow Axes

You can control each axis individually:

```css
.box {
  overflow-x: auto;
  overflow-y: hidden;
}
```

## 3. Use Cases

### Example 1: Truncate Text

```css
.truncate {
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
```

### Example 2: Scrollable Container

```css
.scroll-area {
  height: 200px;
  overflow-y: auto;
}
```

## 4. Notes

- Overflow only works on **block-level** or **positioned** elements with a defined size (`height` or `width`).
- For inline elements, overflow has **no effect** unless converted with `display: block` or similar.