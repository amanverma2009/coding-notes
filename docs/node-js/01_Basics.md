# ![ ](../assets/nodejs-logo.svg) Intro and Setup

## What is Node.js?

Node.js is a **runtime environment** that allows JavaScript to run **outside the browser** using **Chrome's V8 engine**. It's designed for building fast, scalable, and efficient network applications — especially servers and CLI tools.

### Key Features:

* Asynchronous and non-blocking
* Built on event-driven architecture
* JavaScript on the backend
* Fast execution (compiled to machine code)
* Access to built-in modules (fs, http, path, etc.)

## How Node.js Works

Node.js uses an **event loop** and **callback queue** to handle I/O asynchronously:

1. Single-threaded main loop
2. Background threads for I/O via `libuv`
3. Uses callbacks, Promises, or async/await for async flow

## Use Cases

* REST APIs and backend servers
* Real-time apps (chat, games)
* File processing scripts
* Command-line tools
* Microservices architecture

## Setting Up Node.js

### 1. Install Node.js

Download and install from: [https://nodejs.org](https://nodejs.org)
Choose the **LTS version** unless you need the latest features.

### 2. Verify Installation

```bash
node -v    # Node.js version
npm -v     # npm (Node Package Manager) version
```

## Running JavaScript with Node

Create a file:

```js
// hello.js
console.log("Hello from Node.js");
```

Run it in the terminal:

```bash
node hello.js
```

## Node REPL (Read-Eval-Print Loop)

An interactive shell to execute JS line-by-line.

Start it:

```bash
node
```

Try this:

```js
> 5 + 3
8
> const name = "Node"
> name.toUpperCase()
'NODE'
```

Exit:

```plaintext
Ctrl + C (twice)
```

## Summary

| Feature        | Purpose                             |
| -------------- | ----------------------------------- |
| Node.js        | JavaScript runtime on the server    |
| V8 Engine      | Compiles JS to machine code         |
| Event Loop     | Handles async I/O without blocking  |
| REPL           | Test code interactively in terminal |
| `node file.js` | Run JS file outside the browser     |
