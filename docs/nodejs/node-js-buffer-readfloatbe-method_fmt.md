# Node.js Buffer.readFloatBE()方法

> 原文：[https://www.geeksforgeeks.org/node-js-buffer-readfloatbe-method/](https://www.geeksforgeeks.org/node-js-buffer-readfloatbe-method/)

`Buffer.readFloatBE()`方法是`Buffer`模块中类`Buffer`的内置应用编程接口，用于将大端32位浮点值读取到指定偏移量处的已分配缓冲区。

## 语法

```js
Buffer.readFloatBE( offset )
```

## 参数

该方法接受单参数`offset`，指定读取前要跳过的字节数。偏移值为 `0 <= offset <= buffer.length - 4`。它的默认值是0。

## 返回值

以大端格式返回整数值。

以下示例说明了Node.js中`buf.readFloatBE()`方法的使用：

### 示例 1

```js
// Node program to demonstrate the
// Buffer.readFloatBE(INTEGER) method
// Creating a buffer of given size
const buf = Buffer.from([10, 20, 30, 40, 50, 60, 70, 80]);

// Display the result
console.log("Functions of Buffer.readFloatBE(int)");
console.log(buf.readFloatBE(0))
console.log(buf);
```

**输出：**

```js
Functions of Buffer.readFloatBE(int)
7.13161255447549e-33
<Buffer 0a 14 1e 28 32 3c 46 50>
```

### 示例 2

```js
// Node program to demonstrate the
// Buffer.readFloatBE(INTEGER) method
// Creating a buffer of given size
const buf = Buffer.from([100, 200, 300, 400, 500, 600, 700, 800]);

// Display the result
console.log("Functions of Buffer.readFloatBE(int)");
console.log(buf.readFloatBE(5))
console.log(buf);
```

**输出：**

```js
Functions of Buffer.readFloatBE(int)
internal/buffer.js:72
  throw new ERR_OUT_OF_RANGE(type || 'offset',
  ^

RangeError [ERR_OUT_OF_RANGE]: The value of "offset" is out of range.
It must be >= 0 and <= 5. Received 5
```

**注意：** 以上程序使用`node index.js`命令编译运行。

**参考：** [https://nodejs.org/docs/latest-v11.x/api/buffer.html#buffer_buf_readfloatbe_offset](https://nodejs.org/docs/latest-v11.x/api/buffer.html#buffer_buf_readfloatbe_offset)