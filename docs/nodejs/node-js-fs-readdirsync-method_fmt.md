# Node.js `fs.readdirSync()`方法

> 原文：[https://www.geeksforgeeks.org/node-js-fs-readdirsync-method/](https://www.geeksforgeeks.org/node-js-fs-readdirsync-method/)

`fs.readdirSync()`方法用于同步读取给定目录的内容。方法返回一个包含目录中所有文件名或对象的数组。`options`参数可用于更改从方法返回文件的格式。

## 语法

```js
fs.readdirSync( path, options )
```

## 参数

这个方法接受两个参数，如上所述，如下所述：

*   **`path`**：它存储必须从中读取内容的目录的路径。它可以是一个字符串、一个缓冲区或一个网络地址。
*   **`options`**：是一个可用于指定影响该方法的可选参数的对象。它有两个可选参数：
    *   **`encoding`**：是一个字符串值，指定用于回调参数文件名的编码。默认值是`utf8`。
    *   **`withFileTypes`**：是一个布尔值，指定是否将文件作为`fs.Dirent`对象返回。默认值是`false`。

## 返回

返回一个字符串、缓冲区或`fs.Dirent`对象的数组，包含目录中的文件。

下面的例子说明了Node.js中的`fs.readdirSync()`方法：

## 示例

### 示例 1

本示例使用`fs.readdirSync()`方法返回目录中的文件名或文件对象。

```js
// Node.js program to demonstrate the
// fs.readdirSync() method

// Import the filesystem module
const fs = require('fs');

// Function to get current filenames
// in directory
filenames = fs.readdirSync(__dirname);

console.log("\nCurrent directory filenames:");
filenames.forEach(file => {
  console.log(file);
});

// Function to get current filenames
// in directory with "withFileTypes"
// set to "true"

fileObjs = fs.readdirSync(__dirname, { withFileTypes: true });

console.log("\nCurrent directory files:");
fileObjs.forEach(file => {
  console.log(file);
});
```

**输出：**

```js
Current directory filenames:
CONTRUBUTIONS.txt
index.html
index.js
package.json
README.md

Current directory files:
Dirent { name: 'CONTRUBUTIONS.txt', [Symbol(type)]: 1 }
Dirent { name: 'index.html', [Symbol(type)]: 1 }
Dirent { name: 'index.js', [Symbol(type)]: 1 }
Dirent { name: 'package.json', [Symbol(type)]: 1 }
Dirent { name: 'README.md', [Symbol(type)]: 1 }
```

### 示例 2

本示例使用`fs.readdirSync()`方法只返回带有`.md`扩展名的文件名。

```js
// Node.js program to demonstrate the
// fs.readdirSync() method

// Import the filesystem module
const fs = require('fs');
const path = require('path');

// Function to get current filenames
// in directory with specific extension
files = fs.readdirSync(__dirname);

console.log("\nFilenames with the .md extension:");
files.forEach(file => {
  if (path.extname(file) == ".md")
    console.log(file);
})
```

**输出：**

```js
Filenames with the .md extension:
README.md
```

## 参考

[https://nodejs.org/api/fs.html#fs_fs_readdirsync_path_options](https://nodejs.org/api/fs.html#fs_fs_readdirsync_path_options)