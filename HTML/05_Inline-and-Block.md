# HTML Block and Inline Elements

## 1. Block-Level Elements

* Always start on a **new line**
* Occupy the **full width** of the parent container
* Can **contain other block or inline elements**
* Commonly used for **layout and structure**

### Common Block Elements:

* `<div>`
* `<p>`
* `<h1>` to `<h6>`
* `<ul>`, `<ol>`, `<li>`
* `<section>`, `<article>`, `<header>`, `<footer>`
* `<table>`, `<form>`, `<nav>`

### Example:

```html
<div>
  <h2>Heading</h2>
  <p>This is a paragraph inside a block-level div.</p>
</div>
```

### Output:

<pre>
<div><h2>Heading</h2><p>This is a paragraph inside a block-level div.</p></div></pre>

## 2. Inline Elements

* **Do not start** on a new line
* Occupy **only as much width** as necessary
* Can **only contain other inline elements or text**
* Commonly used for **formatting small chunks of text**

### Common Inline Elements:

* `<span>`
* `<a>`
* `<strong>`, `<em>`, `<b>`, `<i>`
* `<img>`
* `<input>`, `<label>`
* `<code>`, `<mark>`, `<abbr>`

### Example:

```html
<p>This is a <span style="color: red;">highlighted</span> word.</p>
```

### Output:

<pre>
<p>This is a <span style="color: red;">highlighted</span> word.</p></pre>

## 3. Key Differences

| Feature          | Block Elements                  | Inline Elements                    |
| ---------------- | ------------------------------- | ---------------------------------- |
| Display behavior | Start on a new line             | Flow within a line                 |
| Width            | Full width of parent by default | Only as wide as content            |
| Contain          | Other block or inline elements  | Only text or other inline elements |
| Use Case         | Layout and structure            | Formatting small chunks of content |

## 4. Mixed Example

```html
<div>
  <p>This is a <strong>bold</strong> word and a <a href="#">link</a>.</p>
</div>
```

### Output:

<pre>
<div><p>This is a <strong>bold</strong> word and a <a href="#">link</a>.</p></div></pre>

## 5. Converting Display Type with CSS

You can convert block elements to inline or vice versa using CSS:

```html
<style>
  div {
    display: inline;
  }

  span {
    display: block;
  }
</style>
```
