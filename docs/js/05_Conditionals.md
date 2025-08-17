# Conditionals

Conditionals control the flow of code by executing different blocks based on **true/false** evaluations.

## 1. `if` Statement

```js
let age = 18;

if (age >= 18) {
  console.log("Adult");
}
```

## 2. `if...else`

```js
if (age >= 18) {
  console.log("Adult");
} else {
  console.log("Minor");
}
```

## 3. `if...else if...else`

```js
if (age < 13) {
  console.log("Child");
} else if (age < 18) {
  console.log("Teen");
} else {
  console.log("Adult");
}
```

## 4. Ternary Operator

Shorthand for `if...else`.

```js
let msg = (age >= 18) ? "Adult" : "Minor";
console.log(msg);
```

## 5. Logical Operators

| Operator | Name | Example          | Result       |         |   |         |                |
| -------- | ---- | ---------------- | ------------ | ------- | - | ------- | -------------- |
| `&&`     | AND  | `a > 0 && b > 0` | true if both |         |   |         |                |
| \`       |      | \`               | OR           | \`a > 0 |   | b > 0\` | true if either |
| `!`      | NOT  | `!isLoggedIn`    | inverse      |         |   |         |                |

## 6. `switch` Statement

Efficient alternative to multiple `if...else if`.

```js
let color = "blue";

switch (color) {
  case "red":
    console.log("Red selected");
    break;
  case "blue":
    console.log("Blue selected");
    break;
  default:
    console.log("No match");
}
```

* `break` is required to prevent fall-through
* `default` runs if no case matches

## 7. Falsy Values

These values are considered `false` in conditionals:

* `false`
* `0`
* `""` (empty string)
* `null`
* `undefined`
* `NaN`

```js
if (!value) {
  console.log("Falsy value");
}
```
