# JavaScript Fetch API

The **Fetch API** is used to make **HTTP requests** (GET, POST, etc.) from the browser. It returns a **Promise**.

## 1. Basic GET Request

```js
fetch("https://api.example.com/data")
  .then(res => res.json())
  .then(data => {
    console.log(data);
  })
  .catch(err => {
    console.error("Fetch error:", err);
  });
```

* `res.json()` parses JSON response
* Always use `.catch()` to handle network errors

## 2. Using `async/await`

```js
async function getData() {
  try {
    const res = await fetch("https://api.example.com/data");
    const data = await res.json();
    console.log(data);
  } catch (err) {
    console.error("Error:", err);
  }
}
```

## 3. POST Request (Sending Data)

```js
fetch("https://api.example.com/users", {
  method: "POST",
  headers: {
    "Content-Type": "application/json"
  },
  body: JSON.stringify({
    name: "Alice",
    age: 25
  })
})
  .then(res => res.json())
  .then(data => console.log(data))
  .catch(err => console.error(err));
```

## 4. Common Options

| Option        | Description                        |
| ------------- | ---------------------------------- |
| `method`      | HTTP method (`GET`, `POST`, etc.)  |
| `headers`     | HTTP headers (e.g. `Content-Type`) |
| `body`        | Payload (for `POST`, `PUT`)        |
| `mode`        | CORS control (`cors`, `no-cors`)   |
| `credentials` | `same-origin`, `include`           |

## 5. Handling Errors Manually

Even if the response is 404/500, `fetch()` **doesn’t throw** — you must check `res.ok`.

```js
async function getUser() {
  const res = await fetch("/api/user");

  if (!res.ok) {
    throw new Error(`HTTP error ${res.status}`);
  }

  const data = await res.json();
  console.log(data);
}
```

## 6. Sending Form Data (Non-JSON)

```js
const formData = new FormData();
formData.append("username", "john");
formData.append("age", 30);

fetch("/submit", {
  method: "POST",
  body: formData
});
```

Use `FormData` when submitting forms without setting headers manually.

## 7. Abort a Request

```js
const controller = new AbortController();

fetch("/api/data", { signal: controller.signal })
  .catch(err => console.error("Aborted"));

controller.abort(); // cancel the request
```
