# v8.Serializer.writeDouble() 方法

> 原文：[https://www.geeksforgeeks.org/node-js-v8-serializer-writedouble-method/](https://www.geeksforgeeks.org/node-js-v8-serializer-writedouble-method/)

`v8.Serializer.writeDouble()` 方法是 `v8` 内置应用编程接口（API）中 `Serializer` 模块的一部分，用于将 JavaScript 数值写入内部缓冲区。它用于自定义序列化程序的内部 `_writeHostObject()` 方法。

## 语法

```js
v8.Serializer.writeDouble( value );
```

## 参数

该方法接受如上所述的单个参数，描述如下：

*   `value`：一个必需的参数，指代要写入内部缓冲区的 JavaScript 数值。

## 返回值

这个方法不返回任何东西，而是将一个 JavaScript 数值写入内部缓冲区。

下面的例子说明了在 Node.js 中如何使用 `v8.Serializer.writeDouble()` 方法：

## 示例

### 示例 1

**文件名：`index.js`**

```js
// Accessing v8 module
const v8 = require('v8');
const serializer = new v8.Serializer();

// Calling v8.serializer.writeDouble() 
serializer.writeDouble(5783.3984);
console.log(serializer.releaseBuffer());
```

使用以下命令运行 `index.js` 文件：

```bash
node index.js
```

**输出：**

```js
<Buffer ba da 8a fd 65 97 b6 40>
```

### 示例 2

**文件名：`index.js`**

```js
// Accessing v8 module
const v8 = require('v8');
const serializer = new v8.Serializer();

// Calling v8.serializer.writeRawBytes() 
console.log(serializer.releaseBuffer());

// User defined Function
function writeDoubleData(data) {
    serializer.writeDouble(data);
    console.log(serializer.releaseBuffer());
}

// Function Call
writeDoubleData(123.44);
```

使用以下命令运行 `index.js` 文件：

```bash
node index.js
```

**输出：**

```js
<Buffer >
<Buffer 5c 8f c2 f5 28 dc 5e 40>
```

## 参考

[https://nodejs.org/api/v8.html#v8_serializer_writedouble_value](https://nodejs.org/api/v8.html#v8_serializer_writedouble_value)