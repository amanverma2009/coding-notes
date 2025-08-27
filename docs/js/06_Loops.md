# ![ ](../assets/js-logo.svg) Loops

Loops let you **repeat a block of code** multiple times, either a fixed number of times or until a condition fails.

## 1. `for` Loop

Use when the number of iterations is known.

```js
for (let i = 0; i < 5; i++) {
  console.log(i);
}
```

* `i = 0` → start
* `i < 5` → condition
* `i++` → increment

## 2. `while` Loop

Runs **while** the condition is true.

```js
let i = 0;
while (i < 5) {
  console.log(i);
  i++;
}
```

## 3. `do...while` Loop

Runs **at least once**, then checks the condition.

```js
let i = 0;
do {
  console.log(i);
  i++;
} while (i < 5);
```

## 4. `for...of` Loop

Iterates over **iterables** like arrays, strings, etc.

```js
let nums = [10, 20, 30];

for (let num of nums) {
  console.log(num);
}
```

## 5. `for...in` Loop

Iterates over **keys** in an object.

```js
const user = { name: "John", age: 30 };

for (let key in user) {
  console.log(key, user[key]);
}
```

## 6. `break` and `continue`

### `break`: exits the loop early.

```js
for (let i = 0; i < 10; i++) {
  if (i === 5) break;
  console.log(i); // 0 to 4
}
```

### `continue`: skips current iteration.

```js
for (let i = 0; i < 5; i++) {
  if (i === 2) continue;
  console.log(i); // 0, 1, 3, 4
}
```

## 7. Looping Arrays with `.forEach()`

```js
let arr = [1, 2, 3];

arr.forEach(function (val) {
  console.log(val);
});
```
