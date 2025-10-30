# ![ ](../assets/nodejs-logo.svg) Error Handling and Debugging

## Handling Errors with try/catch

Use `try/catch` to handle **synchronous** errors.

```js
try {
  const result = riskyFunction();
  console.log(result);
} catch (err) {
  console.error("Error:", err.message);
}
```

### Example:

```js
try {
  const x = y + 1; // y is not defined
} catch (err) {
  console.error("Caught error:", err.message);
}
```

## Handling Async Errors with Promises

```js
fetchData()
  .then((res) => {
    console.log(res);
  })
  .catch((err) => {
    console.error("Error:", err);
  });
```

## Async/Await with try/catch

```js
async function loadData() {
  try {
    const res = await fetchSomething();
    console.log(res);
  } catch (err) {
    console.error("Async Error:", err.message);
  }
}
```

## Emitting and Handling Error Events

Some core modules like streams emit `error` events.

```js
const fs = require("fs");
const stream = fs.createReadStream("missing.txt");

stream.on("error", (err) => {
  console.error("Stream error:", err.message);
});
```

## Throwing Custom Errors

```js
function divide(a, b) {
  if (b === 0) throw new Error("Cannot divide by zero");
  return a / b;
}
```

## Global Error Handlers

Catch unhandled errors:

```js
process.on("uncaughtException", (err) => {
  console.error("Uncaught Exception:", err);
});
```

For unhandled Promise rejections:

```js
process.on("unhandledRejection", (reason) => {
  console.error("Unhandled Rejection:", reason);
});
```

## Debugging

### 1. `console.log`

Simple and fast, use it to inspect values.

```js
console.log("Debug here:", variable);
```

### 2. `debugger` Keyword

Pauses execution like a breakpoint.

```js
function test() {
  const a = 5;
  debugger;
  const b = a + 10;
  return b;
}
```

Run with:

```bash
node inspect app.js
```

Then use `n`, `c`, `repl`, etc. to step through the code.

### 3. VS Code Debugger

* Set breakpoints directly in the editor
* Use launch configuration (`.vscode/launch.json`)
* Run using the built-in debugger
