# DOM Part 2: Modifying Elements

## 1. `innerText`, `textContent`, `innerHTML`

### `innerText`

Returns **visible** text.

```js
element.innerText = "Hello";
```

### `textContent`

Returns **all text**, including hidden.

```js
element.textContent = "Hi";
```

### `innerHTML`

Reads or replaces the **HTML** inside an element.

```js
element.innerHTML = "<strong>Bold text</strong>";
```

## 2. Changing Styles

Use `.style.propertyName` (camelCase for CSS).

```js
element.style.color = "red";
element.style.backgroundColor = "#f0f0f0";
```

## 3. `classList` Methods

### `add()` – Add a class

```js
element.classList.add("active");
```

### `remove()` – Remove a class

```js
element.classList.remove("disabled");
```

### `toggle()` – Add if missing, remove if present

```js
element.classList.toggle("open");
```

### `contains()` – Check if class exists

```js
element.classList.contains("active"); // true/false
```

## 4. Working with Attributes

### `getAttribute()`

```js
let link = element.getAttribute("href");
```

### `setAttribute()`

```js
element.setAttribute("src", "img.png");
```

### `removeAttribute()`

```js
element.removeAttribute("disabled");
```

## 5. Input Values

Use `.value` for form elements.

```js
let input = document.querySelector("#username");
console.log(input.value);       // get
input.value = "newUser123";     // set
```

## 6. Example: Modify Button Text & Style

```js
let btn = document.querySelector("#submit");

btn.innerText = "Sending...";
btn.style.backgroundColor = "gray";
btn.classList.add("disabled");
```
