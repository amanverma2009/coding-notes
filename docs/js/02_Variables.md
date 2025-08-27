# ![ ](../assets/js-logo.svg) Variables

Variables are used to **store data** that can be referenced and manipulated later.

## 1. Declaration Keywords

### a) `var`

* Function-scoped
* Hoisted (can be used before declaration, but unsafe)
* **Avoid using** in modern code

```js
var x = 10;
```

### b) `let`

* Block-scoped
* Can be reassigned
* Preferred for values that change

```js
let count = 5;
count = 6;
```

### c) `const`

* Block-scoped
* Cannot be reassigned
* Must be initialized when declared
* Use for constants or fixed references

```js
const PI = 3.14;
// PI = 3.1415 ❌ Error
```

## 2. Naming Rules

* Case-sensitive
* Must start with letter, `_`, or `$`
* Can’t start with a number
* Use **camelCase** for naming (`userName`, `totalPrice`)

```js
let userName = "Emma";
const MAX_SCORE = 100;
```

## 3. Hoisting Behavior

* `var` is hoisted (declared at top of scope), but value is `undefined`
* `let` and `const` are hoisted but **not initialized** (Temporal Dead Zone)

```js
console.log(x); // undefined
var x = 10;

console.log(y); // ReferenceError
let y = 20;
```

## 4. Reassignment

| Keyword | Reassignable | Scope    |
| ------- | ------------ | -------- |
| `var`   | ✅           | Function |
| `let`   | ✅           | Block    |
| `const` | ❌           | Block    |

## 5. Constants with Objects and Arrays

`const` prevents reassignment of the variable, **not mutation** of its contents.

```js
const user = { name: "Rahul" };
user.name = "Dev"; // ✅ Allowed

const arr = [1, 2, 3];
arr.push(4); // ✅ Allowed
```
