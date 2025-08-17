# Data Types

JavaScript has **8 basic data types**, divided into **primitive** and **reference (non-primitive)** types.

## 1. Primitive Types (Immutable)

Stored directly in the variable.

### a) `String`

Text data.

```js
let name = "Henry";
```

### b) `Number`

Both integers and floats.

```js
let age = 15;
let pi = 3.14;
```

### c) `Boolean`

Logical values.

```js
let isOnline = true;
```

### d) `undefined`

A variable declared but not assigned.

```js
let x;
console.log(x); // undefined
```

### e) `null`

Intentional absence of value.

```js
let data = null;
```

### f) `Symbol` (ES6)

Unique and immutable identifier.

```js
let sym = Symbol("id");
```

### g) `BigInt` (ES2020)

Handles large integers beyond `Number.MAX_SAFE_INTEGER`.

```js
let big = 1234567890123456789012345678901234567890n;
```

## 2. Reference Types (Objects)

Stored as **references** in memory.

### a) `Object`

Collection of key-value pairs.

```js
let user = {
  name: "Aman",
  age: 15
};
```

### b) `Array`

Indexed list of values.

```js
let scores = [90, 85, 100];
```

### c) `Function`

Functions are objects with callable behavior.

```js
function greet() {
  console.log("Hi");
}
```

## 3. Type Checking

Use `typeof` to check types:

```js
typeof "hello";     // "string"
typeof 42;          // "number"
typeof null;        // "object" (bug in JS)
typeof [];          // "object"
typeof undefined;   // "undefined"
```

To check arrays:

```js
Array.isArray([1, 2, 3]); // true
```

## 4. Dynamic Typing

JavaScript is **dynamically typed**, so variables can change type at runtime.

```js
let x = "hello";
x = 123; // valid
```
