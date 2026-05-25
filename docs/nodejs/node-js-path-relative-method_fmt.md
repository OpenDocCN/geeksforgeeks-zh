# Node.js path.relative()方法

> 原文：[https://www.geeksforgeeks.org/node-js-path-relative-method/](https://www.geeksforgeeks.org/node-js-path-relative-method/)

`path.relative()`方法用于根据当前工作目录找到从一个给定路径到另一个路径的相对路径。如果两个给定路径相同，它将解析为零长度字符串。

## 语法

```js
path.relative( from, to )
```

## 参数

该方法接受两个参数：

*   `From`：此文件路径将用作基础路径。
*   `to`：用于查找相对路径的文件路径。

## 返回值

返回路径规范化形式的字符串。

## 示例

下面的程序说明了 Node.js 中的 `path.relative()`方法：

```js
// Node.js program to demonstrate the path.relative() method

// Import the path module
const path = require('path');

path1 = path.relative("geeks/website", "geeks/index.html");
console.log(path1)

path2 = path.relative("users/admin", "admin/files/website");
console.log(path2)

// When both the paths are same
// It returns blank string
path3 = path.relative("users/admin", "users/admin");
console.log(path3)
```

**输出：**

```js
..\index.html
..\..\admin\files\website

```

## 参考

[https://nodejs.org/api/path.html#path_path_relative_from_to](https://nodejs.org/api/path.html#path_path_relative_from_to)