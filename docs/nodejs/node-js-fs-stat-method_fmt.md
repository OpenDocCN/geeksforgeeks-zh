# Node.js `fs.stat()` 方法

> 原文: [https://www.geeksforgeeks.org/node-js-fs-stat-method/](https://www.geeksforgeeks.org/node-js-fs-stat-method/)

`fs.stat()` 方法用于返回给定文件或目录的信息。它返回一个 `fs.Stat` 对象，该对象包含多个属性和方法，可用于获取文件或目录的详细信息。

## 语法

```js
fs.stat( path, options, callback )
```

## 参数

该方法接受三个参数：

*   `path`: 要检查的文件或目录的路径。可以是字符串、Buffer或URL。
*   `options`: 一个对象，可用于指定影响输出的可选参数。它有一个可选参数：
    *   `bigint`: 一个布尔值，指定 `fs.Stat` 对象中的值是否应为 `bigint` 类型。默认值为 `false`。
*   `callback`: 方法执行时将调用的函数。
    *   `err`: 如果方法执行出错，此参数将包含错误对象。
    *   `stats`: 一个 `fs.Stat` 对象。如果成功，它将包含文件路径的详细信息。

## 示例

### 示例 1

本示例使用 `fs.stat()` 方法获取路径的详细信息。

```js
// Node.js program to demonstrate the
// fs.stat() method

// Import the filesystem module
const fs = require('fs');

// Getting information for a file
fs.stat("example_file.txt", (error, stats) => {
  if (error) {
    console.log(error);
  }
  else {
    console.log("Stats object for: example_file.txt");
    console.log(stats);

    // Using methods of the Stats object
    console.log("Path is file:", stats.isFile());
    console.log("Path is directory:", stats.isDirectory());
  }
});

// Getting information for a directory
fs.stat("example_directory.txt", (error, stats) => {
  if (error) {
    console.log(error);
  }
  else {
    console.log("Stats object for: example_directory.txt");
    console.log(stats);

    // Using methods of the Stats object
    console.log("Path is file:", stats.isFile());
    console.log("Path is directory:", stats.isDirectory());
  }
});
```

**输出:**

```js
Stats object for: example_file.txt
Stats {
  dev: 2269,
  mode: 33188,
  nlink: 1,
  uid: 1000,
  gid: 1000,
  rdev: 0,
  blksize: 4096,
  ino: 271,
  size: 0,
  blocks: 0,
  atimeMs: 1582871562365.894,
  mtimeMs: 1582871556897.5554,
  ctimeMs: 1582871556897.5554,
  birthtimeMs: 1582871556897.5554,
  atime: 2020-02-28T06:32:42.366Z,
  mtime: 2020-02-28T06:32:36.898Z,
  ctime: 2020-02-28T06:32:36.898Z,
  birthtime: 2020-02-28T06:32:36.898Z }
Path is file: true
Path is directory: false
Stats object for: example_directory.txt
Stats {
  dev: 2269,
  mode: 33188,
  nlink: 1,
  uid: 1000,
  gid: 1000,
  rdev: 0,
  blksize: 4096,
  ino: 270,
  size: 0,
  blocks: 0,
  atimeMs: 1582871562357.8936,
  mtimeMs: 1582871553413.3396,
  ctimeMs: 1582871553417.3398,
  birthtimeMs: 1582871553413.3396,
  atime: 2020-02-28T06:32:42.358Z,
  mtime: 2020-02-28T06:32:33.413Z,
  ctime: 2020-02-28T06:32:33.417Z,
  birthtime: 2020-02-28T06:32:33.413Z }
Path is file: true
Path is directory: false
```

### 示例 2

本示例使用 `fs.stat()` 方法通过 `bigint` 选项获取文件的详细信息。

```js
// Node.js program to demonstrate the
// fs.stat() method

// Import the filesystem module
const fs = require('fs');

fs.stat("example_file.txt", (error, stats) => {
  console.log(stats);
});

// Using the bigint option to return
// the values in big integer format
fs.stat("example_file.txt", { bigint: true }, (error, stats) => {
  console.log(stats);
});
```

**输出:**

```js
Stats {
  dev: 2269,
  mode: 33188,
  nlink: 1,
  uid: 1000,
  gid: 1000,
  rdev: 0,
  blksize: 4096,
  ino: 271,
  size: 0,
  blocks: 0,
  atimeMs: 1582871562365.894,
  mtimeMs: 1582871556897.5554,
  ctimeMs: 1582871556897.5554,
  birthtimeMs: 1582871556897.5554,
  atime: 2020-02-28T06:32:42.366Z,
  mtime: 2020-02-28T06:32:36.898Z,
  ctime: 2020-02-28T06:32:36.898Z,
  birthtime: 2020-02-28T06:32:36.898Z }
Stats {
  dev: 2269n,
  mode: 33188n,
  nlink: 1n,
  uid: 1000n,
  gid: 1000n,
  rdev: 0n,
  blksize: 4096n,
  ino: 271n,
  size: 0n,
  blocks: 0n,
  atimeMs: 1582871562365n,
  mtimeMs: 1582871556897n,
  ctimeMs: 1582871556897n,
  birthtimeMs: 1582871556897n,
  atime: 2020-02-28T06:32:42.365Z,
  mtime: 2020-02-28T06:32:36.897Z,
  ctime: 2020-02-28T06:32:36.897Z,
  birthtime: 2020-02-28T06:32:36.897Z }
```

## 参考

[https://nodejs.org/api/fs.html#fs_fs_stat_path_options_callback](https://nodejs.org/api/fs.html#fs_fs_stat_path_options_callback)