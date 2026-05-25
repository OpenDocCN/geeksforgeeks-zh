# Node.js `fs.link()`方法

> 原文：[https://www.geeksforgeeks.org/node-js-fs-link-method/](https://www.geeksforgeeks.org/node-js-fs-link-method/)

`fs.link()`方法用于创建到给定路径的硬链接。创建的硬链接仍然指向同一个文件，即使该文件被重命名。硬链接还包含链接文件的实际内容。

## 语法

```js
fs.link( existingPath, newPath, callback )
```

## 参数

该方法接受三个参数，如上所述，如下所述：

*   `Existing path`：它是一个字符串、Buffer或网址，表示必须为其创建符号链接的文件。
*   `New path`：它是一个字符串、Buffer或网址，表示将在其中创建符号链接的文件路径。
*   `callback`：是一个方法，当方法执行时将被调用。
    *   `err`：如果方法失败，将抛出此错误。

## 示例

下面的例子说明了 Node.js 中的 `fs.link()`方法：

### 示例 1

本示例创建到文件的硬链接。

```js
// Node.js program to demonstrate the
// fs.link() method

// Import the filesystem module
const fs = require('fs');

console.log("Contents of the text file:");
console.log(fs.readFileSync('example_file.txt', 'utf8'));

fs.link(__dirname + "\\example_file.txt", "hardlinkToFile", (err) => {
  if (err) console.log(err)
  else {
    console.log("\nHard link created\n");
    console.log("Contents of the hard link created:");
    console.log(fs.readFileSync('hardlinkToFile', 'utf8'));
  }
});
```

**输出：**

```js
Contents of the text file:
This is an example of the fs.link() method.

Hard link created

Contents of the hard created:
This is an example of the fs.link() method.
```

### 示例 2

本示例创建文件的硬链接，并删除原始文件。原始文件的内容仍然可以通过硬链接访问。

```js
// Node.js program to demonstrate the
// fs.link() method

// Import the filesystem module
const fs = require('fs');

console.log("Contents of the text file:");
console.log(fs.readFileSync('example_file.txt', 'utf8'));

fs.link(__dirname + "\\example_file.txt", "hardlinkToFile", (err) => {
  if (err) console.log(err)
  else {
    console.log("\nHard link created\n");
    console.log("Contents of the hard link created:");
    console.log(fs.readFileSync('hardlinkToFile', 'utf8'));

    console.log("\nDeleting the original file");
    fs.unlinkSync("example_file.txt");

    console.log("\nContents of the hard link created:");
    console.log(fs.readFileSync('hardlinkToFile', 'utf8'));
  }
});
```

**输出：**

```js
Contents of the text file:
This is an example of the fs.link() method.

Hard link created

Contents of the hard link created:
This is an example of the fs.link() method.

Deleting the original file

Contents of the hard link created:
This is an example of the fs.link() method.
```

## 参考

[https://nodejs.org/api/fs.html#fs_fs_link_existingpath_newpath_callback](https://nodejs.org/api/fs.html#fs_fs_link_existingpath_newpath_callback)