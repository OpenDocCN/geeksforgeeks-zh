# Node.js Stream 可读流 `readableFlowing` 属性

> 原文: [https://www.geeksforgeeks.org/node-js-stream-readable-readableflowing-property/](https://www.geeksforgeeks.org/node-js-stream-readable-readableflowing-property/)

可读流中的 `readableFlowing` 属性，用于检查流是否处于流动模式。

## 语法

```js
readable.readableFlowing
```

## 返回值

如果流处于流动模式，则返回 `true`，否则返回 `false`。

下面的例子说明了在 Node.js 中 `readableFlowing` 属性的使用:

### 例 1

```js
// Node.js program to demonstrate the
// readable.readableFlowing Property

// Include fs module
var fs = require("fs");
var data = '';

// Create a readable stream
var readerStream = fs.createReadStream('input.txt');

// Handling data event
readerStream.on('data', function(chunk) {
   data += chunk;
});

// Calling readableFlowing property
readerStream.readableFlowing;
```

**输出:**

```js
true
```

### 例 2

```js
// Node.js program to demonstrate the
// readable.readableFlowing Property

// Include fs module
const fs = require("fs");

// Constructing readable stream
const readable = fs.createReadStream("input.txt");

// Instructions for reading data
readable.on('readable', () => {
  let chunk;

// Using while loop and calling
  // read method with parameter
  while (null !== (chunk = readable.read())) {

// Displaying the chunk
    console.log(`read: ${chunk}`);
  }
});

// Calling readable.readableFlowing
// Property
readable.readableFlowing;
```

**输出:**

```js
false
```

**参考:** [https://nodejs.org/api/stream.html#stream_readable_readableflowing](https://nodejs.org/api/stream.html#stream_readable_readableflowing)。