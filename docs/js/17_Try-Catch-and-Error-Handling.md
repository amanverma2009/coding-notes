# ![ ](../assets/js-logo.svg) `try...catch` & Error Handling

`try...catch` is used to **safely handle errors** in synchronous and asynchronous code, preventing crashes and allowing custom responses.

## 1. Basic Syntax

```js
try {
  // Code that might throw an error
} catch (err) {
  // Runs if error occurs
}
```

### Example:

```js
try {
  let x = y + 1; // y is not defined → error
} catch (err) {
  console.log("Error caught:", err.message);
}
```

## 2. `finally` Block

Always runs, whether error occurs or not.

```js
try {
  // risky code
} catch (err) {
  console.log("Handled error");
} finally {
  console.log("This always runs");
}
```

## 3. Error Object

In `catch(err)`, the `err` object contains:

* `name`: error type (e.g. `ReferenceError`)
* `message`: description
* `stack`: call trace (for debugging)

```js
try {
  throw new Error("Something went wrong");
} catch (e) {
  console.log(e.name);    // Error
  console.log(e.message); // Something went wrong
}
```

## 4. Handling Errors in Functions

```js
function divide(a, b) {
  if (b === 0) throw new Error("Cannot divide by zero");
  return a / b;
}

try {
  console.log(divide(10, 0));
} catch (err) {
  console.log("Math error:", err.message);
}
```

## 5. Async + `try/catch`

Always wrap `await` calls in `try/catch`.

```js
async function fetchData() {
  try {
    let res = await fetch("invalid-url");
    let data = await res.json();
  } catch (err) {
    console.log("Fetch failed:", err.message);
  }
}
```

## 6. Best Practices

* Use `try/catch` around **isolated risky logic**
* Don’t overuse — handle only **expected** errors
* Use `finally` for cleanup tasks (e.g. closing connections, hiding loaders)
* Throw custom errors to improve debugging and user messages
