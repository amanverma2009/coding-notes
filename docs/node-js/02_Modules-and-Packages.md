# ![ ](../assets/nodejs-logo.svg) Modules and Packages

## What Are Modules?

Modules are **independent blocks of reusable code**. In Node.js, every file is treated as a **separate module**.

There are three types of modules:

1. Core (built-in)
2. Custom (user-defined)
3. Third-party (npm packages)

## CommonJS (require/module.exports)

### Exporting in one file

```js
// math.js
function add(a, b) {
  return a + b;
}
module.exports = add;
```

### Importing in another

```js
// app.js
const add = require("./math");
console.log(add(2, 3)); // 5
```

You can export multiple values:

```js
module.exports = {
  add,
  subtract
};
```

## ES Modules (import/export)

Supported with `.mjs` extension or `"type": "module"` in `package.json`.

```js
// math.mjs
export function add(a, b) {
  return a + b;
}
```

```js
// app.mjs
import { add } from './math.mjs';
console.log(add(5, 6));
```

## Built-in Modules

Node provides many core modules out of the box. Common ones:

* `fs` – file system
* `path` – file paths
* `http` – create web servers
* `os` – system info
* `events` – event emitter

Example:

```js
const path = require("path");

console.log(__filename);                  // full file path
console.log(path.basename(__filename));  // file name
```

## Creating Custom Modules

Every file is its own module. Use `module.exports` to export, and `require()` to import.

```js
// logger.js
function log(msg) {
  console.log(`[LOG]: ${msg}`);
}
module.exports = log;
```

```js
// main.js
const log = require("./logger");
log("App started");
```

## Intro to npm (Node Package Manager)

npm lets you install and manage third-party packages.

Check version:

```bash
npm -v
```

Initialize a project:

```bash
npm init -y
```

This creates a `package.json` file that stores metadata and dependencies.

## Installing Packages

Install locally:

```bash
npm install chalk
```

Use:

```js
const chalk = require("chalk");
console.log(chalk.green("Success!"));
```

Install globally:

```bash
npm install -g nodemon
```

## Dev Dependencies

Install a package for development only:

```bash
npm install nodemon --save-dev
```

## package.json Basics

```json
{
  "name": "project-name",
  "version": "1.0.0",
  "main": "index.js",
  "scripts": {
    "start": "node index.js",
    "dev": "nodemon index.js"
  },
  "dependencies": {
    "chalk": "^5.0.0"
  },
  "devDependencies": {
    "nodemon": "^2.0.0"
  }
}
```

## package-lock.json

Tracks exact versions of all installed packages to ensure consistency across environments.

## node\_modules

Stores all installed packages. Do **not** push this folder to GitHub — use `.gitignore`.
