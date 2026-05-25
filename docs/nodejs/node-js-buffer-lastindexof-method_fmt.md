# Node.js Buffer.lastIndexOf()方法

> 原文: [https://www.geeksforgeeks.org/node-js-buffer-lastindexof-method/](https://www.geeksforgeeks.org/node-js-buffer-lastindexof-method/)

缓冲区是一种临时内存存储，当数据从一个地方移动到另一个地方时，它存储数据。它就像一个整数数组。

`Buffer.lastIndexOf()`方法检查缓冲区中的给定值，并返回其存在的索引。如果同一个值出现不止一次，那么它将返回该值出现的最后一个索引。

## 语法

```js
Buffer.lastIndexOf( value, byteOffset, encoding )
```

## 参数

该方法接受三个参数，如下所述：

*   `value`: 指定要在缓冲区中搜索的数据。
*   `byteOffset`: 你需要开始搜索缓冲区的索引。其默认值为 `0`。
*   `encoding`: 它持有一个字符串值，该值决定了在缓冲区中搜索的字符串的二进制表示形式。其默认值为 `utf8`。

## 返回值

这个方法返回一个代表索引值的整数值。

下面的例子说明了在 Node.js 中 `Buffer.lastIndexOf()` 方法的使用：

## 示例 1

```js
// Node program to demonstrate the
// Buffer.lastIndexOf() Method

var buffer = Buffer.from('GeeksForGeeks');

console.log(buffer.lastIndexOf('G'));
```

**输出**

```js

```

## 示例 2

```js
// Node program to demonstrate the
// Buffer.lastIndexOf() Method

var buffer = Buffer.from('GeeksForGeeks');

console.log(buffer.lastIndexOf(101));
// Prints : 10
// 101 is the ascii value of 'e'
// e occurs last at index 10

console.log(buffer.lastIndexOf('computer portal'));
//Prints : -1
//as it is not present in the given value
```

**输出:**

```js

```

**注意:** 以上程序使用 `node index.js` 命令编译运行。

**参考:** [https://nodejs.org/api/buffer.html#buffer_buf_lastindexof_value_byteoffset_encoding](https://nodejs.org/api/buffer.html#buffer_buf_lastindexof_value_byteoffset_encoding)