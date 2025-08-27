# ![ ](../assets/nodejs-logo.svg) HTTP and Routing

## HTTP Module

The `http` module lets you create a basic web server without using any external frameworks.

```js
const http = require("http");
```

## Create a Basic Server

```js
const server = http.createServer((req, res) => {
  res.write("Hello from Node.js server");
  res.end();
});

server.listen(3000, () => {
  console.log("Server running on http://localhost:3000");
});
```

## Handling Routes

Use `req.url` to detect the requested path and `req.method` to detect the HTTP method.

```js
const server = http.createServer((req, res) => {
  if (req.url === "/") {
    res.write("Home Page");
  } else if (req.url === "/about") {
    res.write("About Page");
  } else {
    res.writeHead(404);
    res.write("Page Not Found");
  }
  res.end();
});
```

## Sending JSON

```js
if (req.url === "/api") {
  res.writeHead(200, { "Content-Type": "application/json" });
  res.end(JSON.stringify({ name: "Node", version: "1.0" }));
}
```

## Serving HTML Files

```js
const fs = require("fs");

if (req.url === "/home") {
  fs.readFile("index.html", (err, data) => {
    if (err) {
      res.writeHead(500);
      res.end("Server Error");
      return;
    }
    res.writeHead(200, { "Content-Type": "text/html" });
    res.end(data);
  });
}
```

## Handling Query Parameters

```js
const url = require("url");

const server = http.createServer((req, res) => {
  const parsedUrl = url.parse(req.url, true); // true to parse query
  const name = parsedUrl.query.name;
  res.end(`Hello ${name}`);
});
```

Example:
Request to `/greet?name=John` → Response: `Hello John`

## Setting Headers

```js
res.writeHead(200, {
  "Content-Type": "text/plain",
  "Custom-Header": "value"
});
```

## HTTP Status Codes

| Code | Meaning               |
| ---- | --------------------- |
| 200  | OK                    |
| 404  | Not Found             |
| 500  | Internal Server Error |

## Summary

* Use `http.createServer()` to build a server
* Use `req.url` and `req.method` for routing
* Use `fs` to serve files
* Manually handle headers and status codes
