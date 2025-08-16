# File System and Path

## File System (fs module)

The `fs` module allows you to interact with the file system (read, write, update, delete files/directories).

```js
const fs = require("fs");
```

### Read a File (async)

```js
fs.readFile("file.txt", "utf8", (err, data) => {
  if (err) throw err;
  console.log(data);
});
```

### Read a File (sync)

```js
const data = fs.readFileSync("file.txt", "utf8");
console.log(data);
```

### Write a File (overwrite)

```js
fs.writeFile("output.txt", "Hello world", (err) => {
  if (err) throw err;
  console.log("Written successfully");
});
```

### Append to a File

```js
fs.appendFile("output.txt", "\nNew line", (err) => {
  if (err) throw err;
});
```

### Delete a File

```js
fs.unlink("output.txt", (err) => {
  if (err) throw err;
});
```

### Create a Directory

```js
fs.mkdir("myFolder", (err) => {
  if (err) throw err;
});
```

### Read Directory Contents

```js
fs.readdir(".", (err, files) => {
  if (err) throw err;
  console.log(files);
});
```

### Remove a Directory

```js
fs.rmdir("myFolder", (err) => {
  if (err) throw err;
});
```

## fs.promises (modern promise-based API)

```js
const fsPromises = require("fs").promises;

async function readFile() {
  const data = await fsPromises.readFile("file.txt", "utf8");
  console.log(data);
}
```

## Path Module

The `path` module is used to work with file and directory paths in a platform-independent way.

```js
const path = require("path");
```

### Common Methods

```js
__dirname                // current directory
__filename               // current file path

path.basename(__filename)    // just file name
path.dirname(__filename)     // directory name
path.extname(__filename)     // file extension
path.join("folder", "file.txt")  // cross-platform path
path.resolve("folder", "file.txt") // absolute path
```

### Example

```js
const filePath = path.join(__dirname, "data", "info.txt");
console.log(filePath);
```

## Summary

| Task            | Method                           |
| --------------- | -------------------------------- |
| Read file       | `fs.readFile`, `fs.readFileSync` |
| Write file      | `fs.writeFile`, `fs.appendFile`  |
| Delete file     | `fs.unlink`                      |
| Read dir        | `fs.readdir`                     |
| Work with paths | `path.join`, `path.basename`     |
