# Node.js Stream 可写流 `destroy()` 方法

> 原文：`https://www.geeksforgeeks.org/node-js-stream-writable-destroy-method/`

`writable.destroy()` 方法是 Stream 模块的内置 API，用于销毁创建的流。在流被销毁后，不能再次调用 `write()` 方法写入数据。

## 语法

```js
writable.destroy()
```

## 参数

此方法不接受任何参数。

## 返回值

返回 `destroyed` 属性被设置为 `true` 的可写流对象。

## 示例

以下示例说明了 Node.js 中 `writable.destroy()` 方法的使用：

### 示例 1

```js
// Node.js program to demonstrate the
// writable.destroy() method
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

// Again writing some data
writable.write('hello');

// Calling destroy function
writable.destroy();
```

**输出：**

```js
hi
hello
Writable {
  _writableState:
   WritableState {
     objectMode: false,
     highWaterMark: 16384,
     finalCalled: false,
     needDrain: false,
     ending: false,
     ended: false,
     finished: false,
     destroyed: true,
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
     prefinished: false,
     errorEmitted: false,
     emitClose: true,
     autoDestroy: false,
     bufferedRequestCount: 0,
     corkedRequestsFree:
      { next: null,
        entry: null,
        finish: [Function: bound onCorkedFinish] } },
  writable: true,
  _write: [Function: write],
  domain: null,
  _events: [Object: null prototype] {},
  _eventsCount: 0,
  _maxListeners: undefined }
```

因此，创建的流被销毁。

### 示例 2

```js
// Node.js program to demonstrate the
// writable.destroy() method
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

// Again writing some data
writable.write('hello');

// Calling destroy function
writable.destroy();

writable.write('');
```

**输出：**

```js
hi
hello
Error [ERR_STREAM_DESTROYED]: Cannot call write after stream was destroyed
    at doWrite (_stream_writable.js:411:19)
    at writeOrBuffer (_stream_writable.js:399:5)
    at Writable.write (_stream_writable.js:299:11)
    at /home/runner/QuizzicalFluffyOperation/index.js:29:10
    at Script.runInContext (vm.js:133:20)
    at Object. (/run_dir/interp.js:156:20)
    at Module._compile (internal/modules/cjs/loader.js:778:30)
    at Object.Module._extensions..js (internal/modules/cjs/loader.js:789:10)
    at Module.load (internal/modules/cjs/loader.js:653:32)
```

在上面的示例中，发生错误是因为在流被销毁后调用了 `write()` 方法。

## 参考

`https://nodejs.org/api/stream.html#stream_writable_destroy_error`