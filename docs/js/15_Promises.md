# ![ ](../assets/js-logo.svg) Promises

A **Promise** is an object representing the eventual result of an **asynchronous operation** — it may **resolve** (success) or **reject** (failure).

## 1. Creating a Promise

```js
const promise = new Promise((resolve, reject) => {
  let success = true;

  if (success) {
    resolve("Done");
  } else {
    reject("Error");
  }
});
```

## 2. Consuming a Promise

```js
promise
  .then(result => {
    console.log("Resolved:", result);
  })
  .catch(error => {
    console.log("Rejected:", error);
  });
```

## 3. Example: Simulated Async Task

```js
function asyncTask() {
  return new Promise((resolve) => {
    setTimeout(() => {
      resolve("Task complete");
    }, 1000);
  });
}

asyncTask().then(res => console.log(res));
```

## 4. Chaining Promises

```js
doStep1()
  .then(result1 => doStep2(result1))
  .then(result2 => doStep3(result2))
  .then(final => console.log("Final:", final))
  .catch(err => console.error(err));
```

## 5. `Promise.all([])`

Runs multiple promises in parallel, waits for **all**.

```js
Promise.all([p1, p2, p3])
  .then(values => console.log(values))
  .catch(err => console.log(err));
```

## 6. `Promise.race([])`

Returns the result of the **first resolved/rejected** promise.

```js
Promise.race([p1, p2])
  .then(result => console.log("First done:", result));
```

## 7. Promise States

| State       | Description                            |
| ----------- | -------------------------------------- |
| `pending`   | Initial state, neither done nor failed |
| `fulfilled` | Operation completed successfully       |
| `rejected`  | Operation failed                       |

## 8. When to Use Promises

* API calls (`fetch`)
* File reading
* Delayed actions
* Replacing deeply nested callbacks (callback hell)

Use `async/await` for cleaner syntax (covered next).
