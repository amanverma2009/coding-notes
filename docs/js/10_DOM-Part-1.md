# ![ ](../assets/js-logo.svg) DOM Part 1: Basics & Selecting Elements

## 1. What Is the DOM?

**DOM (Document Object Model)** is a tree-like structure where:

* Each **HTML element** is a **node**
* JavaScript can access and manipulate these nodes

The root is `document`.

## 2. Accessing the Document

```js
console.log(document);           // entire DOM
console.log(document.title);     // page title
console.log(document.body);      // <body> element
```

## 3. Selecting Elements

### a) `getElementById`

Selects a single element by ID.

```js
let heading = document.getElementById("main-title");
```

### b) `getElementsByClassName`

Returns a **live HTMLCollection** (not an array).

```js
let items = document.getElementsByClassName("menu-item");
```

Access with index: `items[0]`

### c) `getElementsByTagName`

Returns all elements by tag name.

```js
let allParas = document.getElementsByTagName("p");
```

## 4. `querySelector` & `querySelectorAll`

### `querySelector`

Returns **first match** using **CSS selector**.

```js
let btn = document.querySelector(".btn");       // first .btn
let header = document.querySelector("#header"); // #header
let input = document.querySelector("input[type='text']");
```

### `querySelectorAll`

Returns **NodeList** of **all matches**.

```js
let allButtons = document.querySelectorAll(".btn");
```

Loop with `forEach()`:

```js
allButtons.forEach(btn => btn.classList.add("active"));
```

## 5. NodeList vs HTMLCollection

| Feature             | NodeList            | HTMLCollection       |
| ------------------- | ------------------- | -------------------- |
| Returned by         | `querySelectorAll`  | `getElementsBy*`     |
| Can use `forEach()` | ✅ (modern browsers) | ❌ (convert to array) |
| Live updates        | ❌ static            | ✅ live               |

To convert HTMLCollection:

```js
Array.from(items).forEach(el => console.log(el));
```
