# `async/await`

`async` and `await` are **syntactic sugar** over Promises that make asynchronous code look and behave like synchronous code.

## 1. `async` Function

Declaring a function `async` makes it return a **Promise**.

```js
async function greet() {
  return "Hello";
}

greet().then(msg => console.log(msg)); // "Hello"
```

## 2. `await`

`await` pauses the function until the Promise resolves.

```js
async function loadData() {
  let response = await fetch("https://api.example.com/data");
  let data = await response.json();
  console.log(data);
}
```

* Can only use `await` **inside an `async` function**
* It **waits** for the Promise to resolve

## 3. Try/Catch for Error Handling

Use `try/catch` to handle rejections.

```js
async function getUser() {
  try {
    let res = await fetch("https://api.example.com/user");
    let user = await res.json();
    console.log(user);
  } catch (err) {
    console.error("Failed:", err);
  }
}
```

## 4. Parallel `await` with `Promise.all`

```js
async function loadAll() {
  const [res1, res2] = await Promise.all([
    fetch("/api/one"),
    fetch("/api/two")
  ]);
  const data1 = await res1.json();
  const data2 = await res2.json();
}
```

## 5. Invalid Usage (Don't Do This)

```js
await fetch("/url"); // ❌ SyntaxError: await is only valid in async functions
```

## 6. When to Use

Use `async/await` for:

* Cleaner, readable async logic
* Avoiding `.then()` chains
* Fetching API data
* Sequencing dependent async operations
