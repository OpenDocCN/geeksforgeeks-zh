# Node.js `fs.readlinkSync()`方法

> 原文: [https://www.geeksforgeeks.org/node-js-fs-readlinksync-method/](https://www.geeksforgeeks.org/node-js-fs-readlinksync-method/)

`fs.readlinkSync()`方法是`fs`模块的内置应用编程接口，用于同步返回符号链接的值，即链接到的路径。可选参数可用于指定链接路径的字符编码。

## 语法

```js
fs.readlinkSync( path, options )
```

## 参数

该方法接受两个参数，如上所述，如下所述：

*   `Path`: 一个字符串、Buffer 或 URL，表示符号链接的路径。
*   `Option`: 一个对象或字符串，可用于指定会影响输出的可选参数。它有一个可选参数：
    *   `Code`: 一个字符串值，指定返回链接路径的字符编码。默认值是`utf8`。

下面的例子说明了 Node.js 中的`fs.readlinkSync()`方法。

## 示例 1

```js
// Node.js program to demonstrate the
// fs.readlinkSync() method

// Import the filesystem module
const fs = require('fs');

// Create a symbolic link
fs.symlinkSync(__dirname + "\\example_file.txt",
          "symlinkToFile", 'file');

console.log("\nSymlink created\n");

// Get the path of the symbolic link
symlinkPath = fs.readlinkSync("symlinkToFile");
console.log("Path of the symlink:", symlinkPath);
```

**输出:**

```js
Symlink created

Path of the symlink: G:\tutorials\nodejs-fs-readlinkSync\example_file.txt
```

## 示例 2

本示例创建一个指向目录的符号链接。

```js
// Node.js program to demonstrate the
// fs.readlinkSync() method

// Import the filesystem module
const fs = require('fs');

// Create a symbolic link
fs.symlinkSync(__dirname + 
    "\\example_directory", "symlinkToDir", 'dir');

console.log("\nSymlink created\n");

// Get the path of the symbolic link
symlinkPath = fs.readlinkSync("symlinkToDir");
console.log("Path of the symlink:", symlinkPath);
```

**输出:**

```js
Symlink created

Path of the symlink: G:\tutorials\nodejs-fs-readlinkSync\example_directory
```

**参考:** [https://nodejs.org/api/fs.html#fs_fs_readlinksync_path_options](https://nodejs.org/api/fs.html#fs_fs_readlinksync_path_options)