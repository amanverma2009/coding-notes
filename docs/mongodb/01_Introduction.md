# ![ ](../assets/MongoDB_light.svg#only-light) ![ ](../assets/MongoDB_dark.svg#only-dark) Introduction

## What is MongoDB?

MongoDB is a **NoSQL (non-relational) database** that stores data in a **document-oriented** format using **JSON-like objects** called BSON (Binary JSON). Unlike traditional relational databases that use tables and rows, MongoDB uses **collections** and **documents**.

## Key Features

* **Document-Oriented Storage** – Data is stored in flexible, schema-less JSON-like documents.
* **Scalability** – Supports horizontal scaling using **sharding**.
* **High Performance** – Optimized for read and write operations.
* **Indexing** – Supports various types of indexes to improve query performance.
* **Aggregation Framework** – Used to process data and perform operations like filtering, grouping, and sorting.
* **Replication** – Provides high availability using **replica sets**.

## Basic Terminology

* **Database** – A container for collections.
* **Collection** – A group of related documents (similar to a table in SQL).
* **Document** – A single record in MongoDB stored as a BSON object.
* **Field** – A key-value pair inside a document (similar to a column).
* **_id** – A unique identifier automatically generated for each document.

## Example Document

```json
{
  "_id": 1,
  "name": "Rajesh Singh",
  "age": 25,
  "skills": ["HTML", "CSS", "JavaScript", "Python", "Node.js"]
}
```

## Comparison with SQL Databases

| SQL Database | MongoDB                      |
| ------------ | ---------------------------- |
| Table        | Collection                   |
| Row          | Document                     |
| Column       | Field                        |
| Primary Key  | _id                          |
| Joins        | Embedded Documents / $lookup |
| Schema       | Schema-less                  |

## Advantages

* Flexible data structure (no need to define schema in advance)
* Easy to scale horizontally
* High speed for large-scale applications
* JSON-like syntax makes it developer-friendly

## Use Cases

* Real-time analytics
* Content management systems
* IoT and sensor data storage
* E-commerce platforms
* Social media applications

## Installation & Basic Commands

* **Start MongoDB Shell:**

  ```sh
  mongosh
  ```

* **Show databases:**

  ```sh
  show dbs
  ```

* **Use or create a database:**

  ```sh
  use myDatabase
  ```

* **Show collections:**

  ```sh
  show collections
  ```

* **Insert a document:**

  ```sh
  db.users.insertOne({ name: "Harry", age: 22 })
  ```

* **Find documents:**

  ```sh
  db.users.find()
  ```
