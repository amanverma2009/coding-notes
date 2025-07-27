# Events and Streams

## EventEmitter (events module)

Node.js uses the **EventEmitter** pattern to handle asynchronous events. It's part of the built-in `events` module.

```js
const EventEmitter = require("events");
const emitter = new EventEmitter();
```

## Emitting and Listening to Events

```js
emitter.on("greet", (name) => {
  console.log(`Hello, ${name}`);
});

emitter.emit("greet", "Alice"); // Hello, Alice
```

### Multiple Listeners

You can register multiple listeners to the same event.

```js
emitter.on("log", () => console.log("Listener 1"));
emitter.on("log", () => console.log("Listener 2"));
emitter.emit("log");
```

### Once

Use `.once()` to listen only one time.

```js
emitter.once("data", () => console.log("Received once"));
emitter.emit("data"); // Triggers
emitter.emit("data"); // Ignored
```

### Remove Listener

```js
function log() {
  console.log("Log event");
}

emitter.on("log", log);
emitter.removeListener("log", log);
```

## Streams

Streams handle data **in chunks**, great for large files or network traffic.

Four types:

* Readable
* Writable
* Duplex (read + write)
* Transform (modify during read/write)

## Readable Stream Example

```js
const fs = require("fs");
const readStream = fs.createReadStream("bigfile.txt", "utf8");

readStream.on("data", (chunk) => {
  console.log("Received chunk:", chunk);
});
```

## Writable Stream Example

```js
const writeStream = fs.createWriteStream("output.txt");

writeStream.write("Line 1\n");
writeStream.write("Line 2\n");
writeStream.end();
```

## Pipe

Use `.pipe()` to connect readable to writable stream.

```js
const fs = require("fs");

const input = fs.createReadStream("source.txt");
const output = fs.createWriteStream("copy.txt");

input.pipe(output);
```

## Buffer

Buffers are raw binary data stored in memory outside the V8 heap.

```js
const buf = Buffer.from("Hello");
console.log(buf);           // <Buffer 48 65 6c 6c 6f>
console.log(buf.toString()); // Hello
```

Use Buffers when working with streams, sockets, or binary files.

## Summary

| Concept      | Description                         |
| ------------ | ----------------------------------- |
| EventEmitter | Emit/listen for custom async events |
| Stream       | Handle large data in chunks         |
| Pipe         | Connect readable → writable streams |
| Buffer       | Low-level binary data container     |
