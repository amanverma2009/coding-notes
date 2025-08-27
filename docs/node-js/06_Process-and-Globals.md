# ![ ](../assets/nodejs-logo.svg) Process and Globals

## The `process` Object

`process` is a global object in Node.js that provides information and control over the current Node.js process.

### Access Command Line Arguments

```js
console.log(process.argv);
```

Run:

```bash
node app.js hello world
```

Result:

```js
[
  '/path/to/node',
  '/path/to/app.js',
  'hello',
  'world'
]
```

Use `process.argv.slice(2)` to ignore the first two entries.

### Environment Variables

```js
console.log(process.env.NODE_ENV);
```

Set:

```bash
NODE_ENV=development node app.js
```

Use `.env` files in real apps (with dotenv package).

### Exit Code

```js
process.exit(0); // success
process.exit(1); // failure
```

### Events

```js
process.on("exit", (code) => {
  console.log("Exiting with code:", code);
});
```

## Global Variables

These are available in every Node.js file.

### `__dirname`

Absolute path of the current directory.

```js
console.log(__dirname);
```

### `__filename`

Absolute path of the current file.

```js
console.log(__filename);
```

### `require`

Used to import CommonJS modules.

```js
const fs = require("fs");
```

### `module` and `exports`

Control what a module exposes.

```js
module.exports = {}; // or exports.myFunc = ...
```

## setTimeout and setInterval

Work like in the browser but run in Node’s event loop.

```js
setTimeout(() => {
  console.log("After 1 second");
}, 1000);

const intervalId = setInterval(() => {
  console.log("Repeating");
}, 2000);

setTimeout(() => clearInterval(intervalId), 7000); // stop after 7s
```

## Reading from stdin

```js
process.stdin.on("data", (data) => {
  console.log(`You typed: ${data.toString().trim()}`);
});
```

To use:

```bash
node app.js
# then type something and press Enter
```

## Summary

| Feature        | Description            |
| -------------- | ---------------------- |
| `process.argv` | CLI args               |
| `process.env`  | Environment variables  |
| `__dirname`    | Current directory path |
| `__filename`   | Current file path      |
| `setTimeout`   | Delay execution        |
| `setInterval`  | Repeat execution       |
| `stdin/stdout` | Read/write to terminal |
