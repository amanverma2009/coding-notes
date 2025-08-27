# ![ ](../assets/js-logo.svg) Functions

Functions are reusable blocks of code that perform specific tasks. You define them once and call them anywhere.

## 1. Function Declaration

```js
function greet() {
  console.log("Hello");
}

greet(); // Call the function
```

## 2. Parameters & Arguments

```js
function add(a, b) {
  return a + b;
}

let result = add(5, 3); // 8
```

* `a`, `b` → parameters (placeholders)
* `5`, `3` → arguments (actual values)

## 3. Return Value

Use `return` to send a value back.

```js
function multiply(x, y) {
  return x * y;
}
```

If no `return`, the function returns `undefined`.

## 4. Function Expression

Function stored in a variable.

```js
const greet = function () {
  console.log("Hi");
};

greet();
```

## 5. Arrow Functions (ES6)

Shorter syntax, often used for callbacks.

```js
const add = (a, b) => a + b;
```

With multiple lines:

```js
const greet = () => {
  console.log("Hello");
};
```

## 6. Default Parameters

```js
function sayHello(name = "Guest") {
  console.log("Hello, " + name);
}

sayHello(); // "Hello, Guest"
```

## 7. Rest Parameters

Combines multiple arguments into an array.

```js
function sum(...nums) {
  return nums.reduce((a, b) => a + b);
}

sum(1, 2, 3); // 6

## 8. Anonymous Functions

Functions without a name, often used inline.

```js
setTimeout(function () {
  console.log("Delayed");
}, 1000);
```

## 9. Callback Functions

Function passed as an argument to another function.

```js
function process(data, callback) {
  callback(data);
}

process(5, function (num) {
  console.log(num * 2);
});
```
