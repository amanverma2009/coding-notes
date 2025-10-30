# ![ ](../assets/nodejs-logo.svg) JSON, Timers and CLI Tools

## Working with JSON

JSON (JavaScript Object Notation) is commonly used for configuration, data files, and APIs.

### Read JSON from a File

```js
const fs = require("fs");

const data = fs.readFileSync("data.json", "utf8");
const parsed = JSON.parse(data);

console.log(parsed.name);
```

### Write JSON to a File

```js
const user = { name: "Alice", age: 25 };
const json = JSON.stringify(user, null, 2); // pretty print

fs.writeFileSync("user.json", json);
```

### Parse and Stringify

```js
const obj = JSON.parse('{"name": "Bob"}');
const str = JSON.stringify(obj);
```

## Timers

Node provides timer functions similar to the browser.

### setTimeout

Run a function once after a delay (ms).

```js
setTimeout(() => {
  console.log("Delayed message");
}, 1000);
```

### setInterval

Run a function repeatedly at an interval (ms).

```js
const intervalId = setInterval(() => {
  console.log("Repeats every 2s");
}, 2000);

setTimeout(() => clearInterval(intervalId), 7000); // stop after 7s
```

### setImmediate

Runs a callback after the current event loop phase.

```js
setImmediate(() => {
  console.log("Runs immediately after current task");
});
```

### clearTimeout / clearInterval

Stop scheduled timers.

```js
const id = setTimeout(() => {}, 5000);
clearTimeout(id);
```

## Building CLI Tools

### Reading Command-Line Arguments

```js
const args = process.argv.slice(2);
console.log(args); // ["hello", "world"]
```

Run with:

```bash
node script.js hello world
```

### Simple Flag Parser

```js
const flags = {};
process.argv.slice(2).forEach(arg => {
  const [key, value] = arg.split("=");
  flags[key] = value;
});

console.log(flags);
// node app.js name=alice age=30
// Output: { name: 'alice', age: '30' }
```

### Output with process.stdout

```js
process.stdout.write("Type something: ");
```

### Input with process.stdin

```js
process.stdin.on("data", (data) => {
  console.log(`You typed: ${data.toString().trim()}`);
});
```
