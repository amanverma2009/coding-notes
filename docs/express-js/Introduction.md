# ![ ](../assets/Express.js_light.svg#only-light) ![ ](../assets/Express.js_dark.svg#only-dark) Introduction

Express.js is a **minimal and flexible Node.js web application framework** that provides robust features for building web and mobile applications. It simplifies the process of handling routes, requests, responses, and middleware in Node.js.

## 1. Why Use Express.js?

- Simplifies building server-side applications with Node.js  
- Provides **routing**, **middleware**, and **templating** support  
- Lightweight and fast  
- Widely used in production apps and APIs  

## 2. Installation

First, initialize a Node.js project:

```bash
mkdir express-app
cd express-app
npm init -y
````

Install Express:

```bash
npm install express
```

## 3. Basic Express Server

```js
const express = require("express");
const app = express();
const PORT = 3000;

app.get("/", (req, res) => {
  res.send("Hello, Express!");
});

app.listen(PORT, () => {
  console.log(`Server running on http://localhost:${PORT}`);
});
```

- `express()` creates an Express app
- `app.get(path, callback)` handles GET requests
- `res.send()` sends a response
- `app.listen()` starts the server

## 4. Handling Different Routes

```js
app.get("/about", (req, res) => {
  res.send("About Page");
});

app.post("/submit", (req, res) => {
  res.send("Form Submitted");
});
```

## 5. Middleware

Middleware functions are functions that run **before reaching the final route handler**. They can modify `req` and `res`.

```js
app.use((req, res, next) => {
  console.log(`${req.method} ${req.url}`);
  next();
});
```

## 6. Serving Static Files

```js
app.use(express.static("public"));
```

Now you can serve files like `public/index.html`.

## 7. JSON Data Handling

```js
app.use(express.json());

app.post("/data", (req, res) => {
  res.json({ received: req.body });
});
```

- `express.json()` parses JSON request bodies

## 8. Express Routing in Separate Files

```js
// routes/user.js
const express = require("express");
const router = express.Router();

router.get("/", (req, res) => res.send("User List"));
router.get("/:id", (req, res) => res.send(`User ${req.params.id}`));

module.exports = router;

// app.js
const userRoutes = require("./routes/user");
app.use("/users", userRoutes);
```

Visiting `/users/` → "User List"
Visiting `/users/42` → "User 42"

## 9. Why Express is Popular

- Lightweight but powerful
- Large ecosystem of middleware
- Easy integration with databases like MongoDB, MySQL, PostgreSQL
- Perfect for building **REST APIs** and **full-stack apps**
