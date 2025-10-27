# ![ ](../assets/MongoDB_light.svg#only-light) ![ ](../assets/MongoDB_dark.svg#only-dark)Mongoose

Mongoose is an **Object Data Modeling (ODM)** library for **MongoDB** and **Node.js**.
It helps developers interact with MongoDB using JavaScript objects instead of writing raw database queries.

## Why Use Mongoose?

* Provides **Schema-based** data modeling.
* Offers **validation**, **middleware**, and **query helpers**.
* Handles **relationships** and **data population**.
* Simplifies **CRUD operations** with a clean API.
* Automatically converts JavaScript objects into MongoDB documents.

## Installation

```bash
npm install mongoose
```

## Connecting to MongoDB

```js
import mongoose from "mongoose";

async function connectDB() {
  try {
    await mongoose.connect("mongodb://localhost:27017/myDatabase");
    console.log("MongoDB connected!");
  } catch (err) {
    console.error(err);
  }
}

connectDB();
```

## Defining a Schema

A **schema** defines the structure of documents within a collection.

```js
const userSchema = new mongoose.Schema({
  name: String,
  age: Number,
  email: { type: String, required: true, unique: true }
});
```

## Creating a Model

A **model** is a wrapper around a MongoDB collection that provides CRUD methods.

```js
const User = mongoose.model("User", userSchema);
```

## CRUD Operations

### 1. Create

```js
const newUser = new User({ name: "Luke", age: 16, email: "Luke@example.com" });
await newUser.save();
```

### 2. Read

```js
const users = await User.find(); // Get all users
const user = await User.findOne({ name: "Luke" }); // Find one
const userById = await User.findById("id_here"); // Find by ID
```

### 3. Update

```js
await User.updateOne({ name: "Luke" }, { age: 17 });
await User.findByIdAndUpdate("id_here", { age: 18 }, { new: true });
```

### 4. Delete

```js
await User.deleteOne({ name: "Luke" });
await User.findByIdAndDelete("id_here");
```

## Schema Types

Common field types:

```js
String, Number, Boolean, Date, Array, ObjectId, Buffer
```

Example:

```js
const postSchema = new mongoose.Schema({
  title: String,
  content: String,
  tags: [String],
  author: { type: mongoose.Schema.Types.ObjectId, ref: "User" },
  date: { type: Date, default: Date.now }
});
```

## Schema Validation

```js
const productSchema = new mongoose.Schema({
  name: { type: String, required: true },
  price: { type: Number, min: 0 },
  inStock: { type: Boolean, default: true }
});
```

## Middleware (Hooks)

Run logic **before** or **after** actions like saving or deleting.

```js
userSchema.pre("save", function (next) {
  console.log("Saving user:", this.name);
  next();
});
```

## Virtuals

Computed fields that are **not stored** in the database.

```js
userSchema.virtual("info").get(function () {
  return `${this.name} (${this.age} years old)`;
});
```

## Populate (Relations)

Used to fetch related documents from another collection.

```js
const post = await Post.find().populate("author");
```

## Example Project Structure

```text
project/
├── models/
│   └── userModel.js
├── index.js
└── package.json
```

* **userModel.js**

```js
import mongoose from "mongoose";

const userSchema = new mongoose.Schema({
  name: String,
  email: String,
  age: Number
});

export default mongoose.model("User", userSchema);
```

* **index.js**

```js
import mongoose from "mongoose";
import User from "./models/userModel.js";

await mongoose.connect("mongodb://localhost:27017/testDB");
const user = await User.create({ name: "Luke", email: "Luke@gmail.com", age: 16 });
console.log(user);
```
