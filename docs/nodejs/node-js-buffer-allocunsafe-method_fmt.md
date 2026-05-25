# Node.js Buffer.allocUnsafe() 方法

> 原文：`https://www.geeksforgeeks.org/node-js-buffer-allocunsafe-method/`

`Buffer.allocUnsafe()` 方法是 `Buffer` 模块中内置的类 `Buffer` 的应用编程接口，用于分配给定大小的缓冲区，但不初始化。

## 语法

```js
const Buffer.allocUnsafe(size)
```

## 参数

该方法接受单个参数 `size`，它保存所需的缓冲区大小。

## 返回值

分配给定大小的缓冲区。

下面的例子说明了 `Buffer.allocUnsafe()` 方法在 Node.js 中的使用：

### 例 1

```js
// Node program to demonstrate the
// Buffer.allocUnsafe(size) method

// Creating a buffer of given size
const buf = Buffer.allocUnsafe(10);

// Display the result
console.log("10 size Buffer created");
console.log(buf);
```

**输出：**

```js
10 size Buffer created
<Buffer 88 c4 62 ba 48 02 00 00 a8 c5>
```

### 例 2

```js
// Node program to demonstrate the
// Buffer.allocUnsafe(size) method

// Creating a buffer of given size
const buf = Buffer.allocUnsafe(10);

// Display the result
console.log("Before filling the Buffer");
console.log(buf);

// Fill buffer with element 'G'
buf.fill('G');

// Display the result
console.log("After filling Buffer");
console.log(buf);
```

**输出：**

```js
Before filling the Buffer
<Buffer 88 c4 62 ba 48 02 00 00 a8 c5>
After filling Buffer
<Buffer 47 47 47 47 47 47 47 47 47 47>
```

**注意：** 以上程序将使用 `node myapp.js` 命令编译运行。

**参考：** `https://nodejs.org/dist/latest-v13.x/docs/api/buffer.html#buffer_class_method_buffer_allocunsafe_size`