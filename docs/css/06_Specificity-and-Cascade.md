# Specificity & Cascade

When multiple CSS rules target the same element, the **cascade** and **specificity** determine which rule wins.

## 1. The Cascade

CSS applies rules based on:

1. **Source order** (last rule wins if equal specificity)
2. **Importance** (`!important`)
3. **Specificity**
4. **Origin** (browser default < user styles < author styles)

### Example:

```css
p {
  color: blue;
}

p {
  color: red;
}
```

**Result:** Red (`red` overrides `blue` because it comes later)

## 2. Specificity

Each selector has a **specificity value**:

| Selector Type           | Specificity Value |
| ----------------------- | ----------------- |
| Inline styles           | 1000              |
| ID selectors            | 100               |
| Class/attr/pseudo-class | 10                |
| Element/pseudo-element  | 1                 |

### Example:

```css
/* Specificity: 1 */
p {
  color: green;
}

/* Specificity: 10 */
.text {
  color: blue;
}

/* Specificity: 100 */
#main {
  color: red;
}
```

**Result:** Red wins due to higher specificity.

## 3. `!important`

Overrides all specificity rules (except other `!important` rules with higher specificity).

```css
p {
  color: blue !important;
}
```

Use **sparingly** – it's hard to override and often a sign of poor structure.

## 4. Specificity Comparison

| Selector      | Specificity |
| ------------- | ----------- |
| `h1`          | 1           |
| `.title`      | 10          |
| `#header`     | 100         |
| `style="..."` | 1000        |
| `!important`  | ∞ (kind of) |
