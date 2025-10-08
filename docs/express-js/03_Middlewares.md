# ![ ](../assets/Express.js_light.svg#only-light) ![ ](../assets/Express.js_dark.svg#only-dark) Middlewares

**Middleware** functions in Express.js are functions that execute **before the final route handler**.
They can modify the **request (`req`)**, **response (`res`)**, or even **end the request-response cycle**.

## Basic Example

```js
const express = require("express");
const app = express();

// Middleware function
app.use((req, res, next) => {
  console.log(`${req.method} ${req.url}`);
  next(); // Passes control to the next middleware/route
});

app.get("/", (req, res) => {
  res.send("Home Page");
});

app.listen(3000, () => console.log("Server running on port 3000"));
```

* `app.use()` → Adds middleware to the entire app
* `next()` → Moves to the next middleware or route handler

## Types of Middleware

### 1. **Application-Level Middleware**

```js
app.use((req, res, next) => {
  console.log("Application-level middleware executed");
  next();
});
```

Applies to all routes unless restricted by path:

```js
app.use("/api", (req, res, next) => { ... });
```

### 2. **Router-Level Middleware**

Used with `express.Router()` to apply middleware only to specific routers.

```js
const router = express.Router();

router.use((req, res, next) => {
  console.log("Router-level middleware");
  next();
});

router.get("/", (req, res) => res.send("Users"));

app.use("/users", router);
```

### 3. **Built-in Middleware**

* `express.json()` → Parses JSON data
* `express.urlencoded({ extended: true })` → Parses URL-encoded form data
* `express.static("public")` → Serves static files

```js
app.use(express.json());
app.use(express.static("public"));
```

### 4. **Third-Party Middleware**

You can install and use external middleware packages.

```bash
npm install morgan cors
```

```js
const morgan = require("morgan");
const cors = require("cors");

app.use(morgan("dev")); // Logs requests
app.use(cors());        // Enables CORS
```

### 5. **Error-Handling Middleware**

Used to handle errors globally. Must have **four parameters**.

```js
app.use((err, req, res, next) => {
  console.error(err.stack);
  res.status(500).send("Something broke!");
});
```

## Middleware Flow Example

```js
app.use((req, res, next) => {
  console.log("First middleware");
  next();
});

app.use((req, res, next) => {
  console.log("Second middleware");
  next();
});

app.get("/", (req, res) => {
  res.send("Final Route Handler");
});
```

**Output:**

```text
First middleware
Second middleware
```

Then the response “Final Route Handler” is sent.
