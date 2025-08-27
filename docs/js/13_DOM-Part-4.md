# ![ ](../assets/js-logo.svg) DOM Part 4: Events

## 1. What Are Events?

Events are actions that happen in the browser (click, scroll, keypress, input, etc.). You can run functions in response.

## 2. `addEventListener()`

Attach a function to run when an event occurs.

```js
element.addEventListener("click", function () {
  console.log("Clicked");
});
```

### Common events:

* `click`
* `mouseover` / `mouseout`
* `keydown` / `keyup`
* `input`
* `submit`
* `change`

## 3. Named Function Example

```js
function greet() {
  console.log("Hello");
}

button.addEventListener("click", greet);
```

## 4. Arrow Function Example

```js
button.addEventListener("click", () => {
  console.log("Clicked!");
});
```

## 5. Accessing the Event Object

Every event listener gets an `event` object with info about the action.

```js
element.addEventListener("click", function (event) {
  console.log(event.target); // the element that was clicked
});
```

## 6. Prevent Default Behavior

Use `event.preventDefault()` to stop default actions like form submit or link navigation.

```js
form.addEventListener("submit", function (e) {
  e.preventDefault();
  console.log("Form blocked");
});
```

## 7. Event Delegation

Listen to a parent and handle clicks from child elements using `event.target`.

```js
document.querySelector("ul").addEventListener("click", function (e) {
  if (e.target.tagName === "LI") {
    e.target.classList.toggle("selected");
  }
});
```

## 8. Removing Event Listeners

```js
function handler() {
  console.log("Removed after one use");
  btn.removeEventListener("click", handler);
}

btn.addEventListener("click", handler);
```

## 9. `once` Option

Automatically removes listener after first trigger.

```js
btn.addEventListener("click", () => {
  console.log("Clicked once");
}, { once: true });
```
