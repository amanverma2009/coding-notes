# Strings

Strings represent **text** and are one of the most commonly used data types in JavaScript.

## 1. Creating Strings

```js
let str1 = "Hello";
let str2 = 'World';
let str3 = `Hello, ${str2}`; // Template literal
```

## 2. String Length

```js
let name = "John";
console.log(name.length); // 4
```

## 3. Accessing Characters

```js
let str = "JavaScript";
console.log(str[0]);      // "J"
console.log(str.charAt(2)); // "v"
```

## 4. String Methods

### `toUpperCase()` / `toLowerCase()`

```js
"abc".toUpperCase(); // "ABC"
"XYZ".toLowerCase(); // "xyz"
```

### `indexOf()` / `lastIndexOf()`

```js
"hello".indexOf("l");      // 2
"hello".lastIndexOf("l");  // 3
```

### `includes()`

```js
"hello".includes("he"); // true
```

### `startsWith()` / `endsWith()`

```js
"hello".startsWith("he"); // true
"hello".endsWith("lo");   // true
```

### `slice(start, end)`

```js
"JavaScript".slice(0, 4); // "Java"
```

### `substring(start, end)`

```js
"JavaScript".substring(4, 10); // "Script"
```

### `substr(start, length)` (deprecated)

```js
"JavaScript".substr(4, 3); // "Scr"
```

### `replace()` / `replaceAll()`

```js
"apple pie".replace("pie", "juice"); // "apple juice"
"aaa".replaceAll("a", "b"); // "bbb"
```

### `trim()`, `trimStart()`, `trimEnd()`

```js
"  hello  ".trim(); // "hello"
```

### `split()`

```js
"red,green,blue".split(","); // ["red", "green", "blue"]
```

### `repeat(n)`

```js
"ha".repeat(3); // "hahaha"
```

## 5. Template Literals

Use backticks `` ` `` for multiline and interpolation.

```js
let name = "Alice";
let msg = `Hello, ${name}!`;
```

## 6. Escape Characters

```js
let str = "He said: \"Hello\"";
let path = "C:\\Users\\User";
```

## 7. Comparing Strings

```js
"abc" === "abc"; // true
"abc" > "abd";   // false (lexical order)
```
