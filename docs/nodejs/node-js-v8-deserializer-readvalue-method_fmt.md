# Node.js v8 Deserializer.readValue() 方法

> 原文：[https://www.geeksforgeeks.org/node-js-v8-deserializer-readvalue-method/](https://www.geeksforgeeks.org/node-js-v8-deserializer-readvalue-method/)

`v8.Deserializer.readValue()` 方法是 `v8` 内置应用编程接口（API）中 `Deserializer` 模块的一部分，用于从缓冲区中的序列化数据中读取 JavaScript 值。

## 语法

```js
v8.Deserializer.readValue();
```

## 参数

此方法不接受任何参数。

## 返回值

该方法从缓冲区中存在的序列化表示中读取 JavaScript 值，并在成功读取时返回该值。

下面的例子说明了在 Node.js 中 `v8.Deserializer.readValue()` 方法的使用：

## 示例 1

**文件名：** `index.js`

```js
// Accessing v8 module
const v8 = require('v8');
const serializer = new v8.Serializer();

// Calling v8.serializer.writeValue() 
console.log(serializer.writeValue("GeeksforGeeks"));

// Calling v8.deserializer.readValue() 
const deserializer = new v8.Deserializer(
            serializer.releaseBuffer());

console.log(deserializer.readValue());
```

使用以下命令运行 `index.js` 文件：

```bash
node index.js
```

**输出：**

```js
true
GeeksforGeeks
```

## 示例 2

**文件名：** `index.js`

```js
// Accessing v8 module
const v8 = require('v8');
const serializer = new v8.Serializer();

// Calling v8.serializer.writeValue() 
console.log(serializer.writeValue(839475.3495));
buff = serializer.releaseBuffer();
console.log("buffer data is:");
console.log(buff);

// Calling v8.deserializer.readValue() 
const deserializer = new v8.Deserializer(buff);

console.log("deserialized data: " 
        + deserializer.readValue());
```

使用以下命令运行 `index.js` 文件：

```bash
node index.js
```

**输出：**

```js
true
buffer data is:
<Buffer 4e fc a9 f1 b2 66 9e 29 41>
deserialized data: 839475.3495
```

## 参考资料

[https://nodejs.org/api/v8.html#v8_deserializer_readvalue](https://nodejs.org/api/v8.html#v8_deserializer_readvalue)