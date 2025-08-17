# CSS Selectors

CSS **selectors** target HTML elements to apply styles. They determine **what** gets styled.

## 1. Basic Selectors

### a) Element Selector

Targets all elements of a specific type.

```css
p {
  color: black;
}
```

### b) Class Selector

Targets elements with a specific `class`.

```css
.title {
  font-weight: bold;
}
```

### c) ID Selector

Targets a unique element with a specific `id`.

```css
#main-heading {
  font-size: 32px;
}
```

## 2. Grouping Selectors

Apply the same style to multiple selectors.

```css
h1, h2, h3 {
  font-family: Arial;
}
```

## 3. Combinators

### a) Descendant Selector

Targets elements nested inside another.

```css
div p {
  color: gray;
}
```

### b) Child Selector (`>`)

Targets direct children only.

```css
ul > li {
  list-style: none;
}
```

### c) Adjacent Sibling (`+`)

Targets the first element immediately after another.

```css
h1 + p {
  margin-top: 0;
}
```

### d) General Sibling (`~`)

Targets all siblings after the first.

```css
h1 ~ p {
  color: blue;
}
```

## 4. Attribute Selectors

Target elements based on attributes.

```css
input[type="text"] {
  border: 1px solid #ccc;
}
```

## 5. Pseudo-classes

Target elements based on state or position.

```css
a:hover {
  text-decoration: underline;
}

li:first-child {
  font-weight: bold;
}
```

## 6. Pseudo-elements

Style parts of elements.

```css
p::first-line {
  font-variant: small-caps;
}
```
