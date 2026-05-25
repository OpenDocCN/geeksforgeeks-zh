# Node.js `path.basename()`方法

> 原文：[https://www.geeksforgeeks.org/node-js-path-basename-method/](https://www.geeksforgeeks.org/node-js-path-basename-method/)

`path.basename()`方法用于获取文件路径的文件名部分。使用此方法时，将忽略结尾目录分隔符。

## 语法

```js
path.basename( path, extension )
```

## 参数

该方法接受两个参数，如下所述：

*   `Path`：用于提取文件名的文件路径。
*   `Extension`：这是一个可选的文件扩展名，将从返回的字符串中删除。

## 返回值

返回一个包含路径文件名部分的字符串。如果`path`或`extension`参数不是字符串值，它将引发错误。

下面的程序说明了 Node.js 中的`path.basename()`方法：

## 示例 1：使用 UNIX 文件路径

```js
// Node.js program to demonstrate the
// path.basename() method

// Import the path module
const path = require('path');

path1 = path.basename('/home/user/bash/index.txt');
console.log(path1)

// Using the extension parameter
path2 = path.basename('/home/user/bash/index.txt', '.txt');
console.log(path2)
```

**输出：**

```js
index.txt
index
```

## 示例 2：使用 Windows 文件路径

```js
// Node.js program to demonstrate the
// path.basename() method

// Import the path module
const path = require('path');

path1 = path.basename('C:\\users\\bash\\index.html');
console.log(path1)

// Using the extension parameter
path2 = path.basename('C:\\users\\bash\\index.html', '.html');
console.log(path2)
```

**输出：**

```js
index.html
index
```

## 参考

[https://nodejs.org/docs/latest-v11.x/api/path.html#path_path_basename_path_ext](https://nodejs.org/docs/latest-v11.x/api/path.html#path_path_basename_path_ext)