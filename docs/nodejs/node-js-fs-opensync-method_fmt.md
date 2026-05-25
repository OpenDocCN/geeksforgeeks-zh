# Node.js `fs.openSync()`方法

> 原文：[https://www.geeksforgeeks.org/node-js-fs-opensync-method/](https://www.geeksforgeeks.org/node-js-fs-opensync-method/)

`fs.openSync()`方法是`fs`模块的内置应用编程接口，用于返回代表文件描述符的整数值。

## 语法

```js
fs.openSync( path, flags, mode )
```

## 参数

该方法接受三个参数，如下所述：

*   `path`：要保存文件的路径。其类型为字符串、缓冲区或网络地址。
*   `flag`：保存字符串或数值。其默认值为`"r"`。
*   `mode`：保存字符串或整数值，默认值为`0o666`。

## 返回值

返回一个代表文件描述符的数字。

下面的例子说明了`fs.openSync()`方法在Node.js中的使用：

## 示例 1

```js
// Node.js program to demonstrate the     
// fs.openSync() method

// Including fs module
var fs = require('fs');

// Defining filename
var filename = './myfile';

// Calling openSync method
// with its parameters
var res = fs.openSync(filename, 'r');

// Prints output
console.log(res);
```

**输出：**

```js

```

这里，标志`"r"`表示文件已经被创建，它读取创建的文件。

## 示例 2

```js
// Node.js program to demonstrate the     
// fs.openSync() method

// Including fs module
var fs = require('fs');

// Defining path
var path = require('path');

// Calling openSync method with
// all its parameters
var fd = fs.openSync(path.join(
    process.cwd(), 'input.txt'), 'w', 0o666);

// This will append the content
// of file created above
fs.writeSync(fd, 'GeeksforGeeks');

// Setting timeout
setTimeout(function () {

// Its printed after the file is closed
  console.log('closing file now');

// closing file descriptor
  fs.closeSync(fd);
}, 10000);
console.log("Program done!");
```

**输出：**

```js
Program done!
closing file now
```

这里，标记`"w"`表示文件被创建或覆盖。

## 参考

[https://nodejs.org/api/fs.html#fs_fs_opensync_path_flags_mode](https://nodejs.org/api/fs.html#fs_fs_opensync_path_flags_mode)