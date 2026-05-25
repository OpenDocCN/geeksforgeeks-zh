# Node.js Buffer.writeFloatBE()方法

> 原文：[https://www.geeksforgeeks.org/node-js-buffer-writefloatbe-method/](https://www.geeksforgeeks.org/node-js-buffer-writefloatbe-method/)

`Buffer.writeFloatBE()`方法是`Buffer`模块中类`Buffer`的内置应用编程接口，用于将大端32位浮点值写入指定偏移量处的已分配缓冲区。

## 语法

```js
Buffer.writeFloatBE( value, offset )
```

## 参数

此方法接受两个参数，如下所述：

*   `value`：此参数指定要写入缓冲区的4字节浮点值。它应该是一个有效的32位大端浮点值。当值不是此值时，行为是未定义的。
*   `offset`：它指定写入前要跳过的字节数，或者简单地表示缓冲区中的索引。`offset`的值是`0 <= offset <= buffer.length - 4`。其默认值为0。

## 返回值

该方法返回一个整数值，该整数值是偏移量和以大端格式写入的字节数之和。

下面的例子说明了在Node.js中使用`Buffer.writeFloatBE()`方法：

## 例1

```js
// Node.js program to demonstrate the 
// Buffer.writeFloatBE() method

// Allocating 16bytes buffer
const buf = Buffer.allocUnsafe(16);

// Writing 32bit or 4 byte floating point
// values to the buffer and printing
// returned value to console
console.log(buf.writeFloatBE(0xbabeface, 0));
console.log(buf.writeFloatBE(0x00000000, 4));
console.log(buf.writeFloatBE(0xffffffff, 8));
console.log(buf.writeFloatBE(0xcabcbcbc, 12));

// Printing the buffer
console.log(buf);
```

### 输出

```js
<Buffer 4f 3a be fb 00 00 00 00 4f 80 00 00 4f 4a bc bd>
```

## 例2

```js
// Node.js program to demonstrate the 
// Buffer.writeFloatBE() method

// Allocating 8bytes buffer
const buf = Buffer.allocUnsafe(8);

// Printing buffer before writing value
console.log("Before writing into buffer:");
console.log(buf);

// Writing 32bits or 4 bytes floating
// point values to the buffer and
// printing returned value to console
console.log(buf.writeFloatBE(0xbabebabe, 0));
console.log(buf.writeFloatBE(0xdecade20, 4));

// Printing the buffer after writing into buffer
console.log("After writing into buffer:");
console.log(buf);
```

### 输出

```js
Before writing into buffer:
<Buffer 00 00 00 00 00 00 00 00>

After writing into buffer:
<Buffer 4f 3a be bb 4f 5e ca de>
```

**注意：** 以上程序使用`node index.js`命令编译运行。

**参考：** [https://nodejs.org/api/buffer.html#buffer_buf_writefloatbe_value_offset](https://nodejs.org/api/buffer.html#buffer_buf_writefloatbe_value_offset)