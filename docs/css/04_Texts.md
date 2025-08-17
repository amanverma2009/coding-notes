# CSS Text

CSS provides properties to style and align **text content** in HTML elements.

## 1. Text Color

```css
p {
  color: #333;
}
```

## 2. Text Alignment

```css
h1 {
  text-align: center;
}
```

Values:

* `left` (default)
* `right`
* `center`
* `justify`

## 3. Text Decoration

Used for underlines, overlines, strikethroughs.

```css
a {
  text-decoration: none;
}
```

Common values:

* `none`
* `underline`
* `overline`
* `line-through`

## 4. Text Transform

Controls capitalization.

```css
h2 {
  text-transform: uppercase;
}
```

Options:

* `none`
* `capitalize`
* `uppercase`
* `lowercase`

## 5. Letter Spacing

Space between letters.

```css
p {
  letter-spacing: 1px;
}
```

## 6. Word Spacing

Space between words.

```css
p {
  word-spacing: 5px;
}
```

## 7. Line Height

Controls spacing between lines.

```css
p {
  line-height: 1.5;
}
```

## 8. Text Shadow

Adds shadow to text.

```css
h1 {
  text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
}
```

Syntax: `x-offset y-offset blur-radius color`
