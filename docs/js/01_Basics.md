# ![ ](../assets/js-logo.svg) Introduction

**JavaScript (JS)** is a high-level, interpreted programming language used to make web pages **interactive** — handling user events, updating content dynamically, validating forms, and much more.

## 1. Embedding JavaScript

### a) Inline

```html
<button onclick="alert('Clicked!')">Click Me</button>
```

### b) Internal (inside `<script>` tag)

```html
<script>
  console.log("Hello, world!");
</script>
```

### c) External (best practice)

```html
<script src="script.js"></script>
```

## 2. Output Methods

| Method                    | Description                                       |
| ------------------------- | ------------------------------------------------- |
| `console.log()`           | Logs to browser console                           |
| `alert()`                 | Shows popup alert                                 |
| `document.write()`        | Writes directly to the document (not recommended) |
| `innerText` / `innerHTML` | Updates page content                              |

```js
console.log("Debug message");
alert("Welcome!");
```

## 3. Variables

```js
let name = "Aman";
const PI = 3.14;
var age = 15;
```

* `let` – block-scoped (preferred)
* `const` – cannot be reassigned
* `var` – function-scoped (avoid using)

## 4. Data Types

* String — `"Hello"`
* Number — `42`, `3.14`
* Boolean — `true`, `false`
* Null — `null`
* Undefined — `undefined`
* Object — `{ key: "value" }`
* Array — `[1, 2, 3]`

```js
let x = "Hi";           // string
let y = 123;            // number
let isActive = true;    // boolean
let user = { name: "Aman", age: 16 }; // object
```

## 5. Comments

```js
// Single-line comment

/*
  Multi-line
  comment
*/
```

## 6. Basic Operators

```js
let a = 5 + 3;     // 8
let b = 10 - 4;    // 6
let c = 2 * 3;     // 6
let d = 8 / 2;     // 4
let e = 9 % 4;     // 1
let f = 2 ** 3;    // 8 (exponent)
```

## 7. Basic DOM Manipulation

```html
<p id="demo">Text</p>
<script>
  document.getElementById("demo").innerText = "Changed!";
</script>
```

JavaScript can **select**, **modify**, and **respond** to HTML elements.

## 8. Why JavaScript?

* Runs in the browser (no install needed)
* Works with HTML & CSS for full interactivity
* Essential for modern web apps (forms, animation, logic, APIs)
