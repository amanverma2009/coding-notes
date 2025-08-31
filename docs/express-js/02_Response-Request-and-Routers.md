# ![ ](../assets/Express.js_light.svg#only-light) ![ ](../assets/Express.js_dark.svg#only-dark) Response, Request and Routers

## Response

In Express.js, the **response object (`res`)** represents the HTTP response that an Express app sends when it receives a request.

### Common Response Methods

```js
res.send("Hello, World!");      // Sends plain text/HTML
res.json({ name: "Ronald" });     // Sends JSON response
res.status(404).send("Not Found"); // Sets status code
res.redirect("/home");          // Redirects to another route
res.download("file.pdf");       // Prompts file download
res.end();                      // Ends the response process
```

* `res.send()` → Sends text, HTML, or JSON automatically detected
* `res.json()` → Always sends JSON
* `res.status()` → Sets HTTP status code
* `res.redirect()` → Redirects to another URL

## Request

The **request object (`req`)** contains all information about the HTTP request.

### Common Request Properties

```js
app.get("/profile/:id", (req, res) => {
  console.log(req.params.id);     // Route params
  console.log(req.query.name);    // Query string ?name=aman
  console.log(req.body);          // Data from POST/PUT body
  console.log(req.method);        // HTTP method (GET, POST, etc.)
  console.log(req.url);           // URL of the request
  res.send("Profile Page");
});
```

* `req.params` → Dynamic route parameters
* `req.query` → Query string parameters
* `req.body` → Data sent in the request body (requires middleware like `express.json()`)
* `req.method` → HTTP method
* `req.url` → Request URL

## Routers

Routers help organize routes into separate files for better structure.

### Example of Router

```js
// routes/user.js
const express = require("express");
const router = express.Router();

router.get("/", (req, res) => res.send("User List"));
router.post("/", (req, res) => res.send("Create User"));
router.get("/:id", (req, res) => res.send(`User ${req.params.id}`));

module.exports = router;
```

### Using Router in Main App

```js
// app.js
const express = require("express");
const app = express();
const userRoutes = require("./routes/user");

app.use("/users", userRoutes);

app.listen(3000, () => console.log("Server running on port 3000"));
```

* Visiting `/users/` → "User List"
* Visiting `/users/42` → "User 42"
* Visiting `/users` with POST → "Create User"
