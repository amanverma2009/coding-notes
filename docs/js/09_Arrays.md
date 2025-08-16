# JavaScript Arrays

Arrays are **ordered lists** used to store multiple values in a single variable. They can contain any data type — strings, numbers, objects, functions, etc.

## 1. Creating Arrays

```js
let arr = [10, 20, 30];
let empty = new Array(); // []
```

## 2. Accessing Items

```js
arr[0];     // 10
arr.length; // 3
arr[arr.length - 1]; // Last item
```

## 3. Modifying Items

```js
arr[1] = 99;       // [10, 99, 30]
arr.push(40);      // [10, 99, 30, 40]
arr.pop();         // Removes last → [10, 99, 30]
arr.shift();       // Removes first → [99, 30]
arr.unshift(5);    // Adds to front → [5, 99, 30]
```

## 4. Array Methods

### `push()` / `pop()`

```js
arr.push(100); // add to end
arr.pop();     // remove from end
```

### `shift()` / `unshift()`

```js
arr.shift();     // remove first
arr.unshift(0);  // add to start
```

### `slice(start, end)`

Returns a **shallow copy** of a portion.

```js
let sliced = arr.slice(1, 3); // [99, 30]
```

### `splice(start, deleteCount, ...items)`

Modifies the array (insert/remove/replace).

```js
arr.splice(1, 1);         // Remove 1 item at index 1
arr.splice(1, 0, 88);     // Insert 88 at index 1
```

### `indexOf()` / `includes()`

```js
arr.indexOf(30);   // 2
arr.includes(99);  // true
```

### `join()`

```js
arr.join(", "); // "5, 99, 30"
```

### `reverse()`

```js
arr.reverse(); // In-place reverse
```

### `sort()`

```js
arr.sort(); // Lexicographic sort
arr.sort((a, b) => a - b); // Numeric sort
```

## 5. Looping Arrays

### `for` loop

```js
for (let i = 0; i < arr.length; i++) {
  console.log(arr[i]);
}
```

### `for...of`

```js
for (let val of arr) {
  console.log(val);
}
```

### `forEach()`

```js
arr.forEach((val, i) => {
  console.log(i, val);
});
```

## 6. Higher-Order Methods

### `map()`

```js
let doubled = arr.map(n => n * 2);
```

### `filter()`

```js
let evens = arr.filter(n => n % 2 === 0);
```

### `reduce()`

```js
let sum = arr.reduce((acc, curr) => acc + curr, 0);
```

## 7. Nested Arrays

```js
let grid = [[1, 2], [3, 4]];
console.log(grid[1][0]); // 3
```
