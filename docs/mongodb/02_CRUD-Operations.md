# ![ ](../assets/MongoDB_light.svg#only-light) ![ ](../assets/MongoDB_dark.svg#only-dark) CRUD Operations

## Introduction

CRUD stands for **Create, Read, Update, Delete** - the four basic operations you can perform on a database. MongoDB is a NoSQL database that stores data in JSON-like documents (BSON).

## 1. Create (Insert)

### Insert One Document

```javascript
db.collectionName.insertOne({
    name: "Rahul",
    age: 16,
    city: "Delhi"
});
```

### Insert Many Documents

```javascript
db.collectionName.insertMany([
    { name: "Ravi", age: 17, city: "Mumbai" },
    { name: "Sara", age: 15, city: "Bangalore" }
]);
```

## 2. Read (Query)

### Find All Documents

```javascript
db.collectionName.find();
```

### Find One Document

```javascript
db.collectionName.findOne({ name: "Lily" });
```

### Find with Conditions

```javascript
db.collectionName.find({ age: { $gt: 15 } }); // age greater than 15
```

### Projection (Select Fields)

```javascript
db.collectionName.find({ age: { $gt: 15 } }, { name: 1, city: 1, _id: 0 });
```

## 3. Update

### Update One Document

```javascript
db.collectionName.updateOne(
    { name: "Piyush" },
    { $set: { city: "Noida" } }
);
```

### Update Many Documents

```javascript
db.collectionName.updateMany(
    { age: { $lt: 17 } },
    { $set: { status: "minor" } }
);
```

### Replace a Document

```javascript
db.collectionName.replaceOne(
    { name: "Sara" },
    { name: "Sara", age: 16, city: "Pune" }
);
```

## 4. Delete

### Delete One Document

```javascript
db.collectionName.deleteOne({ name: "Ravi" });
```

### Delete Many Documents

```javascript
db.collectionName.deleteMany({ age: { $lt: 16 } });
```

## 5. Common Operators

* `$gt` → Greater than
* `$lt` → Less than
* `$gte` → Greater than or equal
* `$lte` → Less than or equal
* `$ne` → Not equal
* `$in` → Matches any value in an array
* `$nin` → Matches none in an array
* `$set` → Updates specified fields
* `$unset` → Removes specified fields

## Example Flow

```javascript
// 1. Create
db.students.insertOne({ name: "Chris", age: 16, grade: "10th" });

// 2. Read
db.students.find({ age: { $gte: 16 } });

// 3. Update
db.students.updateOne({ name: "Chris" }, { $set: { grade: "11th" } });

// 4. Delete
db.students.deleteOne({ name: "Chris" });
```
