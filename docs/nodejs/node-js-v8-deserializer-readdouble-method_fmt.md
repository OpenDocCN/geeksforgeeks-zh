# Node.js v8.Deserializer.readDouble()方法

> 原文: [https://www.geeksforgeeks.org/node-js-v8-deserializer-readdouble-method/](https://www.geeksforgeeks.org/node-js-v8-deserializer-readdouble-method/)

`v8.Deserializer.readDouble()`方法是 v8 的内置 API，属于 `v8.Deserializer` 模块，用于从缓冲区读取 JS 数字。通常在自定义反序列化程序的 `_readHostObject()` 内部使用。

## 语法

```js
v8.Deserializer.readDouble();
```

## 参数

此方法不接受任何参数。

## 返回值

该方法从缓冲区读取 JS 数字并返回。

下面的例子说明了在 Node.js 中 `v8.Deserializer.readDouble()` 方法的使用：

### 示例 1

**文件名: index.js**

```js
// Accessing v8 module
const v8 = require('v8');
const serializer = new v8.Serializer();

// Calling v8.serializer.writeDouble() 
serializer.writeDouble(57839.83475);

// Calling v8.deserializer.readDouble() 
const deserializer = new v8.Deserializer(serializer.releaseBuffer());

console.log(deserializer.readDouble());
```

使用以下命令运行 `index.js` 文件:

```bash
node index.js
```

**输出:**

```
57839.83475
```

### 示例 2

**文件名: index.js**

```js
// Accessing v8 module
const v8 = require('v8');
const serializer = new v8.Serializer();

// Calling v8.serializer.writeDouble() 
console.log(serializer.releaseBuffer());
serializer.writeDouble(29698.674673);
buff = serializer.releaseBuffer();
console.log("buffer data is:");
console.log(buff);

// Calling v8.deserializer.readDouble() 
const deserializer = new v8.Deserializer(buff);
console.log("deserialized data: ");
console.log(deserializer.readDouble());
```

使用以下命令运行 `index.js` 文件:

```bash
node index.js
```

**输出:**

```
<Buffer >
buffer data is:
<Buffer a0 a9 d7 2d ab 00 dd 40>
deserialized data:
29698.674673
```

**参考:** [https://nodejs.org/api/v8.html#v8_deserializer_readdouble](https://nodejs.org/api/v8.html#v8_deserializer_readdouble)