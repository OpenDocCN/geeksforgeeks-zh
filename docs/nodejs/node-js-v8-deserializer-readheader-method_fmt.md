# Node.js v8.Deserializer.readHeader()方法

> 原文: [https://www.geeksforgeeks.org/node-js-v8-deserializer-readheader-method/](https://www.geeksforgeeks.org/node-js-v8-deserializer-readheader-method/)

`v8.Deserializer.readHeader()`方法是`v8`模块的内置API，用于读取标头并对其进行验证，以确保包含有效的序列化格式版本。

## 语法

```js
v8.Deserializer.readHeader();
```

## 参数

此方法不接受任何参数。

## 返回值

这个方法读取反序列化器的头缓冲区并验证它。它在有效的头上返回`true`，否则抛出一个错误。

下面的例子说明了在Node.js中`v8.Deserializer.readHeader()`方法的使用：

### 示例 1

**文件名:** `index.js`

```js
// Accessing v8 module
const v8 = require('v8');
const serializer = new v8.Serializer();

// Calling v8.Deserializer.readHeader() 
console.log(serializer.releaseBuffer());
serializer.writeHeader();

const deserializer = new v8.Deserializer(
            serializer.releaseBuffer());
console.log(deserializer.readHeader());

console.log(serializer.releaseBuffer());
```

使用以下命令运行`index.js`文件：

```bash
node index.js
```

**输出:**

```js
<Buffer >
true
<Buffer >
```

### 示例 2

**文件名:** `index.js`

```js
// Accessing v8 module
const v8 = require('v8');
const serializer = new v8.Serializer();

// Calling v8.serializer.writeHeader() 
serializer.writeHeader();

// Calling v8.deserializer.readHeader() 
const deserializer = new v8.Deserializer(
        serializer.releaseBuffer());

if (deserializer.readHeader()) {
    console.log("It is a valid header!");
} else {
    console.log("It is not a valid header!");
}
```

使用以下命令运行`index.js`文件：

```bash
node index.js
```

**输出:**

```js
It is a valid header!
```

**参考:** [https://nodejs.org/api/v8.html#v8_deserializer_readheader](https://nodejs.org/api/v8.html#v8_deserializer_readheader)