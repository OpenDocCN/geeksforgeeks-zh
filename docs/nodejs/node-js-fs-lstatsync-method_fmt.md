# Node.js `fs.lstatSync()` 方法

> 原文：[https://www.geeksforgeeks.org/node-js-fs-lstatsync-method/](https://www.geeksforgeeks.org/node-js-fs-lstatsync-method/)

`fs.lstatSync()` 方法用于同步返回用于引用文件或目录的符号链接的信息。`fs.Stats` 对象返回几个字段和方法来获取文件的更多细节。

## 语法

```js
fs.lstatSync( path, options )
```

## 参数

该方法接受两个参数，如下所述：

*   **`path`**：一个字符串、Buffer 或 URL，包含符号链接的路径。
*   **`options`**：一个对象，可用于指定影响输出的可选参数。它有一个可选参数：
    *   **`bigint`**：一个布尔值，指定 `fs.Stats` 对象中返回的值是否为 `bigint`。默认值为 `false`。

## 返回值

返回一个包含符号链接详细信息的 `fs.Stats` 对象。

## 示例

以下示例说明了 Node.js 中的 `fs.lstatSync()` 方法：

### 示例 1

本示例使用 `fs.lstatSync()` 方法获取文件符号链接的详细信息。

```js
// Node.js program to demonstrate the
// fs.lstatSync() method

// Import the filesystem module
const fs = require('fs');

fs.symlinkSync(__dirname + "\\example_file.txt",
                       "symlinkToFile", 'file');

console.log("Symlink to file created")

statsObj = fs.lstatSync("symlinkToFile");

console.log("Stat of symlinkToFile")
console.log(statsObj);
```

**输出：**

```js
Symlink to file created
Stat of symlinkToFile
Stats {
  dev: 3229478529,
  mode: 41398,
  nlink: 1,
  uid: 0,
  gid: 0,
  rdev: 0,
  blksize: 4096,
  ino: 281474976780954,
  size: 49,
  blocks: 0,
  atimeMs: 1585207963423.2476,
  mtimeMs: 1585207963423.2476,
  ctimeMs: 1585207963423.2476,
  birthtimeMs: 1585207963423.2476,
  atime: 2020-03-26T07:32:43.423Z,
  mtime: 2020-03-26T07:32:43.423Z,
  ctime: 2020-03-26T07:32:43.423Z,
  birthtime: 2020-03-26T07:32:43.423Z
}
```

### 示例 2

本示例使用 `fs.lstatSync()` 方法获取指向文件夹的符号链接的详细信息。

```js
// Node.js program to demonstrate the
// fs.lstatSync() method

// Import the filesystem module
const fs = require('fs');

fs.symlinkSync(__dirname + "\\example_directory",
                      "symlinkToDir", 'dir');

console.log("Symlink to directory created")

statsObj = fs.lstatSync("symlinkToDir");
console.log("Stat of symlinkToDir")
console.log(statsObj);
```

**输出：**

```js
Stat of symlinkToDir
Stats {
  dev: 3229478529,
  mode: 41398,
  nlink: 1,
  uid: 0,
  gid: 0,
  rdev: 0,
  blksize: 4096,
  ino: 281474976780955,
  size: 50,
  blocks: 0,
  atimeMs: 1585208001112.3284,
  mtimeMs: 1585208001112.3284,
  ctimeMs: 1585208001112.3284,
  birthtimeMs: 1585208001112.3284,
  atime: 2020-03-26T07:33:21.112Z,
  mtime: 2020-03-26T07:33:21.112Z,
  ctime: 2020-03-26T07:33:21.112Z,
  birthtime: 2020-03-26T07:33:21.112Z
}
```

## 参考

[https://nodejs.org/api/fs.html#fs_fs_lstatsync_path_options](https://nodejs.org/api/fs.html#fs_fs_lstatsync_path_options)