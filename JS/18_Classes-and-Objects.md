# JavaScript Classes & Objects

JavaScript supports **object-oriented programming (OOP)** using **classes** (ES6+) and **constructor functions**. Classes help organize related data and behavior into reusable blueprints.

## 1. Creating a Class

```js
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  greet() {
    console.log(`Hi, I'm ${this.name}`);
  }
}
```

## 2. Creating Objects (Instances)

```js
const user1 = new Person("Alice", 25);
user1.greet(); // Hi, I'm Alice
```

## 3. Constructor Method

* `constructor()` is called automatically when using `new`
* Used to initialize object properties

```js
class Car {
  constructor(brand, year) {
    this.brand = brand;
    this.year = year;
  }
}
```

## 4. Adding Methods

Define methods directly inside the class:

```js
class Circle {
  constructor(radius) {
    this.radius = radius;
  }

  area() {
    return Math.PI * this.radius ** 2;
  }
}
```

## 5. Class Expression (Anonymous or Named)

```js
const Animal = class {
  constructor(type) {
    this.type = type;
  }
};
```

## 6. Inheritance (`extends`)

One class can inherit from another.

```js
class Animal {
  speak() {
    console.log("Generic sound");
  }
}

class Dog extends Animal {
  speak() {
    console.log("Bark");
  }
}

const d = new Dog();
d.speak(); // Bark
```

## 7. `super()` Keyword

Calls the constructor or method from the parent class.

```js
class Animal {
  constructor(name) {
    this.name = name;
  }
}

class Cat extends Animal {
  constructor(name, color) {
    super(name);
    this.color = color;
  }
}
```

## 8. Static Methods

Static methods belong to the class, not instances.

```js
class MathUtil {
  static square(x) {
    return x * x;
  }
}

MathUtil.square(4); // 16
```

## 9. Object vs Class

* **Object literal**: used for single instances
* **Class**: used for creating multiple objects with shared structure

```js
// Object literal
const user = {
  name: "Bob",
  greet() {
    console.log("Hi");
  }
};
```

Use object literals for simple structures, classes for reusable templates.
