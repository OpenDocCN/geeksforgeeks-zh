# Node.js `fs.mkdtemp()` 方法

> 原文：[https://www.geeksforgeeks.org/node-js-fs-mkdtemp-method/](https://www.geeksforgeeks.org/node-js-fs-mkdtemp-method/)

## 方法描述

`fs.mkdtemp()` 方法用于创建唯一的临时目录。文件夹名称是通过在前缀字符串后面附加 6 个随机生成的字符来创建的。也可以通过在文件夹路径后使用分隔符在文件夹内创建临时目录。

## 语法

```js
fs.mkdtemp( prefix, options, callback )
```

## 参数

该方法接受三个参数，如下所述：

*   `prefix`：一个字符串，将始终在创建目录的六个随机生成的数字之前使用。
*   `option`：一个带有 `encoding` 属性的字符串或对象，可用于指定要使用的字符编码。
*   `callback`：一个在方法执行时将被调用的函数。
    *   `err`：如果操作失败，将抛出此错误。
    *   `folder`：函数创建的临时文件夹的路径。

## 示例

下面的例子说明了 Node.js 中的 `fs.mkdtemp()` 方法：

### 示例 1

本示例在当前目录中创建一个前缀为“temp-”的临时目录。

```js
// Node.js program to demonstrate the
// fs.mkdtemp() method

// Import the filesystem module
const fs = require('fs');

fs.mkdtemp("temp-", (err, folder) => {
  if (err)
    console.log(err);
  else {
    console.log("The temporary folder path is:", folder);
  }
});
```

**输出：**

```js
The temporary folder path is: temp-2jEcWI
```

### 示例 2

本示例在操作系统的临时目录中创建一个临时文件夹。

```js
// Node.js program to demonstrate the
// fs.mkdtemp() method

// Import the filesystem module
const fs = require('fs');

// Import the os module
const os = require('os');

// Get the separator from the path module
const { sep } = require('path');

// Get the temporary directory of the system
const tmpDir = os.tmpdir();

fs.mkdtemp(`${tmpDir}${sep}`, (err, folder) => {
  if (err)
    console.log(err);
  else {
    console.log("The temporary folder path is:", folder);
  }
});
```

**输出：**

```js
The temporary folder path is: C:\Users\userone\AppData\Local\Temp\2avQ7n
```

## 参考

[https://nodejs.org/api/fs.html#fs_fs_mkdtemp_prefix_options_callback](https://nodejs.org/api/fs.html#fs_fs_mkdtemp_prefix_options_callback)