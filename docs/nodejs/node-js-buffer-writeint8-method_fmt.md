# Buffer.writeInt8()方法

> 原文: [https://www.geeksforgeeks.org/node-js-buffer-writeint8-method/](https://www.geeksforgeeks.org/node-js-buffer-writeint8-method/)

`Buffer.writeInt8()`方法是`Buffer`模块中类`Buffer`的内置应用编程接口，用于将值写入指定偏移量处的已分配缓冲区。

## 语法

```js
Buffer.writeInt8( value, offset )
```

## 参数

该方法接受两个参数，如下所述：

*   `value`：此参数指定要写入缓冲区的数字或值。当值不是整数值时，行为是未定义的。
*   `offset`：它指定写入前要跳过的字节数，或者简单地表示缓冲区中的索引。`offset`的值是`0 <= offset <= buffer.length - 1`。其默认值为0。

## 返回值

这个方法返回一个整数值，它是偏移量和写入字节数的和。

## 例子

下面的例子说明了在Node.js中使用`Buffer.writeInt8()`方法：

### 例 1

```js
// Node.js program to demonstrate the 
// Buffer.writeInt8() method

// Allocating buffer of size 4
const buf = Buffer.allocUnsafe(4);

// Writing 8 bit numbers to its
// specified offset and printing
// returned value to console
console.log(buf.writeInt8(20, 0));
console.log(buf.writeInt8(-128, 1));
console.log(buf.writeInt8(-3, 2));
console.log(buf.writeInt8(127, 3));

// Printing buffer to console
console.log(buf);
```

**输出:**

```js
<Buffer 14 80 fd 7f>
```

### 例 2

```js
// Node.js program to demonstrate the 
// Buffer.writeInt8() method

// Allocating buffer of size 2
const buf = Buffer.allocUnsafe(2);

// Printing the buffer before writing into it
console.log("Before writing into buffer:");
console.log(buf);

// Writing 8 bit signed integers
console.log(buf.writeInt8(96, 0));
console.log(buf.writeInt8(-69, 1));

// Printing buffer after writing
// 8 bit signed integers in it.
console.log("After writing into buffer:");
console.log(buf);
```

**输出:**

```js
Before writing into buffer:
<Buffer 98 98>

After writing into buffer:
<Buffer 60 bb>
```

**注意:** 以上程序使用`node index.js`命令编译运行。

**参考:** [https://nodejs.org/api/buffer.html#buffer_buf_writeint8_value_offset](https://nodejs.org/api/buffer.html#buffer_buf_writeint8_value_offset)