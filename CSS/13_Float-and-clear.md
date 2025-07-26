# CSS Float and Clear

The `float` property allows elements to be **taken out of normal flow** and positioned to the **left or right**, with text/content flowing around them. `clear` is used to **prevent wrapping** around floated elements.

---

## 1. `float` Property

| Value   | Description                     |
| ------- | ------------------------------- |
| `left`  | Floats the element to the left  |
| `right` | Floats the element to the right |
| `none`  | Default, no float               |

### Example:

```css
img {
  float: left;
  margin-right: 10px;
}
```

**Result:** The image floats to the left, and the text wraps around it on the right.

## 2. Effects of Float

* Floated elements are **removed from normal flow**
* Parent containers may **collapse** if all children are floated

## 3. `clear` Property

Prevents elements from wrapping around floated siblings.

| Value   | Description                     |
| ------- | ------------------------------- |
| `left`  | Clears floats on the left side  |
| `right` | Clears floats on the right side |
| `both`  | Clears both sides               |
| `none`  | Default                         |

### Example:

```css
.clearfix {
  clear: both;
}
```

Used to push content **below** floated elements.

## 4. Clearing Floats (Fixing Collapsing Parent)

Floats can cause a container to collapse if it has no non-floated children.

### a) Using Clearfix

```css
.clearfix::after {
  content: "";
  display: table;
  clear: both;
}
```

Apply `.clearfix` to the parent container.

## 5. Float vs Flex/Grid

**Use float only for small layouts** (e.g., image wrap).

Avoid it for full layouts — prefer `flex` or `grid` for proper alignment, responsiveness, and readability.
