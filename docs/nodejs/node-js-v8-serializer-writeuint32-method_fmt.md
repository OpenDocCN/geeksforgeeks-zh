# Node.js v8.Serializer.writeUint32()方法

> 原文: [https://www.geeksforgeeks.org/node-js-v8-serializer-writeuint32-method/](https://www.geeksforgeeks.org/node-js-v8-serializer-writeuint32-method/)

`v8.Serializer.writeUint32()`方法是`v8`内置的`Serializer`模块的API，用于将原始32位整数值写入内部缓冲区。它用于自定义序列化程序内部的`_writeHostObject()`。

## 语法:

```js
v8.Serializer.writeUint32( value );
```

## 参数:

该方法接受一个参数：

*   `value`: 必需的参数，指要写入内部缓冲区的32位整数。

## 返回值:

这个方法不返回任何东西，而是将一个原始的32位整数值写入内部缓冲区。

下面的例子说明了在Node.js中`v8.Serializer.writeUint32()`方法的使用：

## 例 1:

### 文件名:

```js
// Accessing v8 module
const v8 = require('v8');
const serializer = new v8.Serializer();

// Calling v8.serializer.writeUint32() 
// The undefined will be logged in 
// console as this function does not
// return anything
console.log(serializer.writeUint32(5783));
console.log(serializer.releaseBuffer());
```

使用以下命令运行`index.js`文件:

```js
node index.js
```

### 输出:

```js
Undefined
<Buffer 97 2d>
```

## 例 2:

### 文件名:

```js
// Accessing v8 module
const v8 = require('v8');
const serializer = new v8.Serializer();

// Calling v8.serializer.writeUint32() 
console.log(serializer.releaseBuffer());
serializer.writeUint32(29698);
console.log(serializer.releaseBuffer());

// Writing two 32 bits number one
// after another
console.log("writing two 32 bits "
    + "number one after another");

serializer.writeUint32(29698);
serializer.writeUint32(29698);
console.log(serializer.releaseBuffer());

console.log("reading after write");

// Calling v8.serializer.writeUint32() 
serializer.writeUint32(5783);

// Calling v8.deserializer.readUint32() 
const deserializer = new 
    v8.Deserializer(serializer.releaseBuffer());
console.log(deserializer.readUint32());
```

使用以下命令运行`index.js`文件:

```js
node index.js
```

### 输出:

```js
<Buffer >
<Buffer 82 e8 01>
writing two 32 bits number one after another
<Buffer 82 e8 01 82 e8 01>
reading after write
```

**参考:** [https://nodejs.org/api/v8.html#v8_serializer_writeuint32_value](https://nodejs.org/api/v8.html#v8_serializer_writeuint32_value)