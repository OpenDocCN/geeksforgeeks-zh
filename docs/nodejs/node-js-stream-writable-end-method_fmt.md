# Node.js Stream 可写流 `end()` 方法

> 原文：[https://www.geeksforgeeks.org/node-js-stream-writable-end-method/](https://www.geeksforgeeks.org/node-js-stream-writable-end-method/)

`writable.end()` 方法是 `Stream` 模块的内置 API，调用它表示将不再有数据写入可写流。参数 `chunk` 和 `encoding` 是可选的，这允许在关闭流之前立即写入最后一个数据块。此外，可选的 `callback` 函数会被添加为可写流 `finish` 事件的监听器。

## 语法

```js
writable.end(chunk, encoding, callback)
```

## 参数

该方法接受三个参数，如下所述：

*   `chunk`：可选的数据块。该值必须是字符串、`Buffer` 或 `Uint8Array`。对于对象模式，`chunk` 可以是除 `null` 外的任何值。
*   `encoding`：如果 `chunk` 是字符串，则此参数指定编码。
*   `callback`：可选的流结束时的回调函数。

## 返回值

它返回调用此方法之前写入的数据。如果 `end()` 方法被调用时带有 `chunk` 数据，那么该数据也会在末尾被返回。

下面的例子说明了在 Node.js 中 `writable.end()` 方法的使用：

## 例 1

```js
// Node.js program to demonstrate the
// writable.end() method

// Including stream module
const stream = require('stream');

// Creating a stream and creating
// a write function
const writable = new stream.Writable({
  // Write function with its
  // parameters
  write: function(chunk, encoding, next) {
    // Converting the chunk of
    // data to string
    console.log(chunk.toString());
    next();
  }
});

// Writing data
writable.write('hi');

// Calling end method with its
// all the parameters
writable.end("last data", "utf8", () => {
  console.log("Writable stream ended!");
});
```

## 输出

```js
hi
last data
Writable {
  _writableState:
   WritableState {
     objectMode: false,
     highWaterMark: 16384,
     finalCalled: false,
     needDrain: false,
     ending: true,
     ended: true,
     finished: false,
     destroyed: false,
     decodeStrings: true,
     defaultEncoding: 'utf8',
     length: 0,
     writing: false,
     corked: 0,
     sync: false,
     bufferProcessing: false,
     onwrite: [Function: bound onwrite],
     writecb: null,
     writelen: 0,
     bufferedRequest: null,
     lastBufferedRequest: null,
     pendingcb: 2,
     prefinished: true,
     errorEmitted: false,
     emitClose: true,
     autoDestroy: false,
     bufferedRequestCount: 0,
     corkedRequestsFree:
      { next: null,
        entry: null,
        finish: [Function: bound onCorkedFinish] } },
  writable: false,
  _write: [Function: write],
  domain: null,
  _events:
   [Object: null prototype] {
     finish: { [Function: bound onceWrapper] listener: [Function] } },
  _eventsCount: 1,
  _maxListeners: undefined }
Writable stream ended!
```

## 例 2

```js
// Node.js program to demonstrate the
// writable.end() method

// Including stream module
const stream = require('stream');

// Creating a stream and creating
// a write function
const writable = new stream.Writable({
  // Write function with its
  // parameters
  write: function(chunk, encoding, next) {
    // Converting the chunk of
    // data to string
    console.log(chunk.toString());
    next();
  }
});

// Writing data
writable.write('hi');

// Calling end method with its
// all the parameters
writable.end("last data", "utf8", () => {
  console.log("Writable stream ended!");
});
writable.write('GfG');
```

## 输出

```js
hi
last data
Error [ERR_STREAM_WRITE_AFTER_END]: write after end
    at writeAfterEnd (_stream_writable.js:248:12)
    at Writable.write (_stream_writable.js:296:5)
    at /home/runner/LuxuriousLegitimateObservation/index.js:30:10
    at Script.runInContext (vm.js:133:20)
    at Object. (/run_dir/interp.js:156:20)
    at Module._compile (internal/modules/cjs/loader.js:778:30)
    at Object.Module._extensions..js (internal/modules/cjs/loader.js:789:10)
    at Module.load (internal/modules/cjs/loader.js:653:32)
    at tryModuleLoad (internal/modules/cjs/loader.js:593:12)
    at Function.Module._load (internal/modules/cjs/loader.js:585:3)
Writable stream ended!
```

这里显示一个错误，因为在 `end()` 方法之后调用 `write()` 方法是不可能的。

## 参考

[https://nodejs.org/api/stream.html#stream_writable_end_chunk_encoding_callback](https://nodejs.org/api/stream.html#stream_writable_end_chunk_encoding_callback)