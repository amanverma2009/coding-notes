# ![ ](../assets/html-logo.svg) Basics

## What is HTML?

**HTML** stands for **HyperText Markup Language**. It is the **standard markup language** used to create and structure content on the web.

### Key Points:

* HTML describes the **structure** of a web page using **elements** (also called **tags**).
* Elements are enclosed in angle brackets: `<tagname>...</tagname>`.
* Most elements have an **opening tag**, **content**, and a **closing tag**.
* HTML files use the `.html` extension.

## Structure of an HTML Document

### Basic Boilerplate:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Page Title</title>
  </head>
  <body>
    <h1>Hello World!</h1>
  </body>
</html>
```

### Explanation of Each Part:

| Section                     | Purpose                                                                 |
| --------------------------- | ----------------------------------------------------------------------- |
| `<!DOCTYPE html>`           | Declares the document type and version (HTML5). Must be the first line. |
| `<html lang="en">`          | Root element of the page. `lang="en"` indicates English content.        |
| `<head>`                    | Contains metadata about the document (not visible content).             |
| `<meta charset="UTF-8">`    | Sets the character encoding (UTF-8 supports all characters).            |
| `<meta name="viewport"...>` | Ensures the site is mobile responsive by controlling page scaling.      |
| `<title>`                   | Sets the title shown in the browser tab.                                |
| `<body>`                    | Contains everything visible on the page (text, images, elements, etc).  |

## Basic Tags and Their Use

### Headings

```html
<h1>Heading 1</h1>
<h2>Heading 2</h2>
<!-- up to <h6> -->
```

### Paragraphs

```html
<p>This is a paragraph.</p>
```

### Links

```html
<a href="https://example.com">Visit Example</a>
```

### Images

```html
<img src="image.jpg" alt="Description of image" />
```

### Lists

#### Unordered:

```html
<ul>
  <li>Item 1</li>
  <li>Item 2</li>
</ul>
```

#### Ordered:

```html
<ol>
  <li>First</li>
  <li>Second</li>
</ol>
```

### Line Break & Horizontal Rule

```html
<br>   <!-- Line break -->
<hr>   <!-- Horizontal line -->
```

## Nesting and Indentation

Elements can be **nested** inside others. Always indent child elements to improve readability.

```html
<ul>
  <li>
    <a href="#">Nested Link</a>
  </li>
</ul>
```

## Comments in HTML

```html
<!-- This is a comment -->
```

Used to add notes or temporarily disable parts of code.
