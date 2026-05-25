# Node.js `fs.realpath()`方法

> 原文: [https://www.geeksforgeeks.org/node-js-fs-realpath-method/](https://www.geeksforgeeks.org/node-js-fs-realpath-method/)

`fs.realpath()`方法用于计算给定路径的规范路径名。它通过解析路径中的`.`、`..`和符号链接来实现。

## 语法

```js
fs.realpath( path, options, callback )
```

## 参数

该方法接受三个参数，如下所述：

*   **`path`**: 要解析的目录路径。可以是一个字符串、Buffer或URL。
*   **`options`**: 一个字符串或对象，用于指定影响操作的可选参数。它有一个可选参数：
    *   **`encoding`**: 一个字符串，定义了解析路径的字符编码。
*   **`callback`**: 方法执行时将被调用的函数。
    *   **`err`**: 如果操作失败，将抛出此错误。
    *   **`resolvedPath`**: 一个字符串或Buffer，表示解析后的规范路径。

下面的例子说明了Node.js中的`fs.realpath()`方法：

## 示例 1

本示例使用`fs.realpath()`方法获取给定路径的规范路径。

```js
// Node.js program to demonstrate the
// fs.realPath() method

// Import the filesystem module
const fs = require('fs');

console.log("Current Directory Path:", __dirname);

// Finding the canonical path
// one directory up
path1 = __dirname + "\\..";

fs.realpath(path1, (error, resolvedPath) => {
  if (error) {
    console.log(error);
  }
  else {
    console.log("One directory up resolved"
      + " path is: ", resolvedPath);
  }
});

// Finding the canonical path
// two directories up
path2 = __dirname + "\\..\\..";

fs.realpath(path2, (error, resolvedPath) => {
  if (error) {
    console.log(error);
  }
  else {
    console.log("Two directories up resolved"
          + " path is:", resolvedPath);
  }
});
```

**输出:**

```js
Current Directory Path: G:\tutorials\nodejs-fs-realPath
Two directories up resolved path is: G:\
One directory up resolved path is: G:\tutorials
```

## 示例 2

本示例使用`fs.realpath()`方法演示不同的编码类型。

```js
// Node.js program to demonstrate the
// fs.realPath() method

// Import the filesystem module
const fs = require('fs');

path = __dirname + "\\..";

// Getting the canonical path in utf8 encoding
fs.realpath(path, {encoding: "utf8"}, (error, resolvedPath) => {
  if (error) {
    console.log(error);
  }
  else {
    console.log("The resolved path is:", resolvedPath);
  }
});

// Getting the canonical path in hex encoding
fs.realpath(path, {encoding: "hex"}, (error, resolvedPath) => {
  if (error) {
    console.log(error);
  }
  else {
    console.log("The resolved path is:", resolvedPath);
  }
});

// Getting the canonical path in base64 encoding
fs.realpath(path, {encoding: "base64"}, (error, resolvedPath) => {
  if (error) {
    console.log(error);
  }
  else {
    console.log("The resolved path is:", resolvedPath);
  }
});
```

**输出:**

```js
The resolved path is: G:\tutorials
The resolved path is: 473a5c7475746f7269616c73
The resolved path is: RzpcdHV0b3JpYWxz
```

## 参考

[https://nodejs.org/api/fs.html#fs_fs_realpath_path_options_callback](https://nodejs.org/api/fs.html#fs_fs_realpath_path_options_callback)