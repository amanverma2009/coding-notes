# JavaScript Callbacks

A **callback** is a function passed as an argument to another function, to be **called later** — either after an operation completes or at a specific time.

## 1. Basic Callback Example

```js
function greet(name) {
  console.log("Hello, " + name);
}

function processUser(callback) {
  let name = "Alice";
  callback(name);
}

processUser(greet); // "Hello, Alice"
```

## 2. Anonymous Callback

```js
setTimeout(function () {
  console.log("Executed after 1 second");
}, 1000);
```

## 3. Arrow Function Callback

```js
setTimeout(() => {
  console.log("Arrow callback");
}, 500);
```

## 4. Array Method Callbacks

### `forEach`

```js
[1, 2, 3].forEach(num => {
  console.log(num);
});
```

### `map`

```js
let doubled = [1, 2, 3].map(n => n * 2);
```

### `filter`

```js
let even = [1, 2, 3, 4].filter(n => n % 2 === 0);
```

## 5. Why Use Callbacks?

* Handle **asynchronous** tasks (API calls, timeouts)
* Reuse logic
* Custom behavior passed into functions

## 6. Callback Hell (Bad Practice)

Nested callbacks make code hard to read:

```js
doTask1(() => {
  doTask2(() => {
    doTask3(() => {
      console.log("Done");
    });
  });
});
```

Use **Promises** or `async/await` to fix this.
