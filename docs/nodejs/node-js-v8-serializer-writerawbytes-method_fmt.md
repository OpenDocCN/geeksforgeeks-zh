# Node.js v8.Serializer.writeRawBytes()方法

> 原文: [https://www.geeksforgeeks.org/node-js-v8-serializer-writerawbytes-method/](https://www.geeksforgeeks.org/node-js-v8-serializer-writerawbytes-method/)

**v8.Serializer.writeRawBytes()方法**是 v8 的内置应用编程接口。串行器模块，用于将原始缓冲区数据写入内部缓冲区。用于自定义序列化程序内部。`_writeHostObject()`。

## 语法:

```js
v8.Serializer.writeRawBytes( Buffer );
```

## 参数:

该方法接受如上所述的单个参数，描述如下:

*   `buffer`: 是一个必需的选项，指要写入内部缓冲区的 buffer/typed array/data view。

## 返回值:

这个方法不返回任何东西，而是将原始缓冲区数据写入内部缓冲区。

下面的例子说明了 v8 的使用。Node.js 中的 `Serializer.writeRawBytes()`方法

## 示例 1:

**文件名:** `index.js`

```js
// Accessing v8 module
const v8 = require('v8');
const serializer = new v8.Serializer();

// Calling v8.serializer.writeRawBytes() 
serializer.writeRawBytes(v8.serialize(5783));
console.log(serializer.releaseBuffer());
```

使用以下命令运行 `index.js` 文件:

```js
node index.js
```

**输出:**

```js
<Buffer ff 0d 49 ae 5a>
```

## 示例 2:

**文件名:** `index.js`

```js
// Accessing v8 module
const v8 = require('v8');
const serializer = new v8.Serializer();

// Calling v8.serializer.writeRawBytes() 
console.log(serializer.releaseBuffer());

// User defined Function
function writeRawData(data) {
    serializer.writeRawBytes(v8.serialize(data));
    console.log("" + serializer.releaseBuffer());
}

// Function Call
writeRawData("GeeksforGeeks");
```

使用以下命令运行 `index.js` 文件:

```js
node index.js
```

**输出:**

```js
<Buffer >
GeeksforGeeks
```

## 参考:

[https://nodejs.org/api/v8.html#v8_serializer_writerawbytes_buffer](https://nodejs.org/api/v8.html#v8_serializer_writerawbytes_buffer)