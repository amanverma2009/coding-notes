# Objects

Objects are key-value pairs used to store **structured data**. Each key is a **property**, and its value can be any data type.

## 1. Object Creation

### a) Object Literal

```js
const user = {
  name: "John",
  age: 30,
  isAdmin: true
};
```

### b) Using `new Object()`

```js
const user = new Object();
user.name = "John";
user.age = 30;
```

## 2. Accessing Properties

### a) Dot Notation

```js
console.log(user.name); // "John"
```

### b) Bracket Notation

```js
console.log(user["age"]); // 30
```

Use brackets when:

* The key has spaces or special characters
* Accessing dynamically

```js
let key = "isAdmin";
console.log(user[key]); // true
```

## 3. Modifying Properties

```js
user.name = "Mike";
user["age"] = 25;
```

## 4. Adding Properties

```js
user.email = "test@example.com";
```

## 5. Deleting Properties

```js
delete user.isAdmin;
```

## 6. Nested Objects

```js
const product = {
  name: "Phone",
  specs: {
    ram: "8GB",
    storage: "128GB"
  }
};

console.log(product.specs.ram); // "8GB"
```

## 7. Methods (Functions inside objects)

```js
const person = {
  firstName: "Jane",
  greet() {
    console.log("Hello!");
  }
};

person.greet(); // "Hello!"
```

## 8. Looping through Objects

### `for...in` loop

```js
for (let key in user) {
  console.log(key, user[key]);
}
```

## 9. Built-in Object Methods

```js
Object.keys(user);    // ["name", "age"]
Object.values(user);  // ["John", 30]
Object.entries(user); // [["name", "John"], ["age", 30]]
```
