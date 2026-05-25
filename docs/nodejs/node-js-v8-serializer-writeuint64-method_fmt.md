# v8.Serializer.writeUint64() 方法

> 原文：[https://www.geeksforgeeks.org/node-js-v8-serializer-writeuint64-method/](https://www.geeksforgeeks.org/node-js-v8-serializer-writeuint64-method/)

`v8.Serializer.writeUint64()` 方法是 v8 内置应用编程接口（API）`Serializer` 模块的一部分，用于将原始 64 位整数值拆分为高 32 位整数和低 32 位整数，并写入内部缓冲区。它通常在自定义序列化程序的内部 `_writeHostObject()` 方法中使用。

## 语法

```js
v8.Serializer.writeUint64(Value_high, Value_low);
```

## 参数

该方法接受两个参数：

*   `Value_high`：必填参数，表示要写入内部缓冲区的 64 位整数的高 32 位。
*   `Value_low`：必填参数，表示要写入内部缓冲区的 64 位整数的低 32 位。

## 返回值

此方法不返回任何内容，而是将原始的 64 位整数值写入内部缓冲区。

下面的例子说明了在 Node.js 中如何使用 `v8.Serializer.writeUint64()` 方法：

## 示例 1

**文件名：**

```js
// Accessing v8 module
const v8 = require('v8');
const serializer = new v8.Serializer();

// Calling v8.serializer.writeUint64() method
// Nothing is returned so, this should
// print undefined
console.log(serializer.writeUint64(5783, 78374));
console.log(serializer.releaseBuffer());
```

使用以下命令运行 `index.js` 文件：

```js
node index.js
```

**输出：**

```js
undefined
<Buffer a6 e4 84 80 f0 d2 05>
```

## 示例 2

**文件名：**

```js
// Accessing v8 module
const v8 = require('v8');
const serializer = new v8.Serializer();

// Calling v8.serializer.writeUint64()
console.log(serializer.releaseBuffer());
serializer.writeUint64(29698, 3847);
console.log(serializer.releaseBuffer());

// Trying to write two 64 bit numbers
// one after another
serializer.writeUint64(29698, 3847);
serializer.writeUint64(29698, 3847);
console.log(serializer.releaseBuffer());

// Reading after write
// Calling v8.serializer.writeUint64()
serializer.writeUint64(6783, 348072);

// Calling v8.deserializer.readUint64()
const deserializer = new
    v8.Deserializer(serializer.releaseBuffer());
console.log(deserializer.readUint64());
```

使用以下命令运行 `index.js` 文件：

```js
node index.js
```

**输出：**

```js
<Buffer >
<Buffer 87 9e 80 80 a0 80 1d>
<Buffer 87 9e 80 80 a0 80 1d 87 9e 80 80 a0 80 1d>
[ 6783, 348072 ]
```

## 参考

[https://nodejs.org/api/v8.html#v8_serializer_writeuint64_hi_lo](https://nodejs.org/api/v8.html#v8_serializer_writeuint64_hi_lo)