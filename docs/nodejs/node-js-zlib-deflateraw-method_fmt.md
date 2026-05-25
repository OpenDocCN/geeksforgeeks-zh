# Node.js zlib.deflateRaw()方法

> 原文: [https://www.geeksforgeeks.org/node-js-zlib-deflateraw-method/](https://www.geeksforgeeks.org/node-js-zlib-deflateraw-method/)

`zlib.deflateRaw()`方法是`zlib`模块的内置API，用于压缩一大块数据。

语法:
```js
zlib.deflateRaw( buffer, options, callback )
```

参数: 该方法接受三个参数，如下所述:
* `buffer`: 可以是`Buffer`、`TypedArray`、`DataView`、`ArrayBuffer`和`string`类型。
* `options`: 是一个可选参数，用于保存`zlib`选项。
* `callback`: 它持有回调函数。

返回值: 返回压缩后的数据块。

以下示例说明了在Node.js中使用`zlib.deflateRaw()`方法:

例 1:
```js
// Node.js program to demonstrate the     
// deflateRaw() method

// Including zlib module
const zlib = require("zlib");

// Declaring input and assigning
// it a value string
var input = "Nidhi Singh";

// Calling deflateRaw method
zlib.deflateRaw(input, (err, buffer) => {

console.log(buffer.toString('hex'));

});
```

输出:
```js
f3cb4cc9c85408cecc4bcf0000 
```

例 2:
```js
// Node.js program to demonstrate the     
// deflateRaw() method

// Including zlib module
const zlib = require("zlib");

// Declaring input and assigning
// it a value string
var input = "GeeksforGeeks";

// Calling deflateRaw method
zlib.deflateRaw(input, (err, buffer) => {

if(!err) {
    console.log(buffer.toString('hex'));
  } 
  else {
    console.log(err);
  }
});
```

输出:
```js
734f4dcd2e4ecb2f7207d100 
```

参考: [https://nodejs.org/api/zlib.html#zlib_zlib_deflateraw_buffer_options_callback](https://nodejs.org/api/zlib.html#zlib_zlib_deflateraw_buffer_options_callback)