# Node.js `fs.fstatSync()`方法

> 原文：[https://www.geeksforgeeks.org/node-js-fs-fstatsync-method/](https://www.geeksforgeeks.org/node-js-fs-fstatsync-method/)

`fs.fstatSync()`方法用于同步返回给定文件描述符的信息。`fs.Stat`对象返回几个字段和方法来获取文件的更多细节。

## 语法

```js
fstatSync( fd, options )
```

## 参数

该方法接受两个参数，如上所述，如下所述：

*   `fd`：一个整数值，表示此方法使用的文件描述符。
*   `option`：一个可用于指定影响输出的可选参数的对象。它有一个可选参数：
    *   `bigint`：一个布尔值，指定在`fs.Stat`对象中返回的值是否为`bigint`。默认值为`false`。

以下示例说明了 Node.js 中的`fs.fstatSync()`方法：

## 示例

### 示例 1

本示例使用`fs.fstatSync()`方法获取文件和目录的详细信息。

```js
// Node.js program to demonstrate the
// fs.fstatSync() method

// Import the filesystem module
const fs = require('fs');

const file_fd = fs.openSync('example_file.txt', 'r');

// Getting information for a file
let fileStat = fs.fstatSync(file_fd);

console.log("Stats object for: example_file.txt");
console.log(fileStat);

// Using methods of the Stats object
console.log("Path is file:", fileStat.isFile());
console.log("Path is directory:", fileStat.isDirectory());

const dir_fd = fs.openSync('example_directory', 'r');

// Getting information for a directory
let dirStat = fs.fstatSync(dir_fd);

console.log("Stats object for: example_directory");
console.log(dirStat);

// Using methods of the Stats object
console.log("Path is file:", dirStat.isFile());
console.log("Path is directory:", dirStat.isDirectory());
```

**输出：**

```js
Stats object for: example_file.txt
Stats {
  dev: 3229478529,
  mode: 33206,
  nlink: 1,
  uid: 0,
  gid: 0,
  rdev: 0,
  blksize: 4096,
  ino: 281474976780786,
  size: 0,
  blocks: 0,
  atimeMs: 1584961030299.117,
  mtimeMs: 1582209885466.6848,
  ctimeMs: 1582209885466.6848,
  birthtimeMs: 1584961030299.117,
  atime: 2020-03-23T10:57:10.299Z,
  mtime: 2020-02-20T14:44:45.467Z,
  ctime: 2020-02-20T14:44:45.467Z,
  birthtime: 2020-03-23T10:57:10.299Z
}
Path is file: true
Path is directory: false
Stats object for: example_directory
Stats {
  dev: 3229478529,
  mode: 16822,
  nlink: 1,
  uid: 0,
  gid: 0,
  rdev: 0,
  blksize: 4096,
  ino: 281474976780789,
  size: 0,
  blocks: 0,
  atimeMs: 1584961090214.9436,
  mtimeMs: 1581074249467.7114,
  ctimeMs: 1584961030324.12,
  birthtimeMs: 1584961030324.12,
  atime: 2020-03-23T10:58:10.215Z,
  mtime: 2020-02-07T11:17:29.468Z,
  ctime: 2020-03-23T10:57:10.324Z,
  birthtime: 2020-03-23T10:57:10.324Z
}
Path is file: false
Path is directory: true
```

### 示例 2

本示例使用`fs.fstatSync()`方法获取带有或不带有`bigint`选项的文件的详细信息。

```js
// Node.js program to demonstrate the
// fs.fstatSync() method

// Import the filesystem module
const fs = require('fs');

const file_fd = fs.openSync('example_file.txt', 'r');

let fileStat = fs.fstatSync(file_fd);
console.log(fileStat);

// Using the bigint option to return
// the values in big integer format
let fileBigIntStat = fs.fstatSync(file_fd, { bigint: true });
console.log(fileBigIntStat);
```

**输出：**

```js
Stats {
  dev: 3229478529,
  mode: 33206,
  nlink: 1,
  uid: 0,
  gid: 0,
  rdev: 0,
  blksize: 4096,
  ino: 281474976780786,
  size: 0,
  blocks: 0,
  atimeMs: 1584961030299.117,
  mtimeMs: 1582209885466.6848,
  ctimeMs: 1582209885466.6848,
  birthtimeMs: 1584961030299.117,
  atime: 2020-03-23T10:57:10.299Z,
  mtime: 2020-02-20T14:44:45.467Z,
  ctime: 2020-02-20T14:44:45.467Z,
  birthtime: 2020-03-23T10:57:10.299Z
}
BigIntStats {
  dev: 3229478529n,
  mode: 33206n,
  nlink: 1n,
  uid: 0n,
  gid: 0n,
  rdev: 0n,
  blksize: 4096n,
  ino: 281474976780786n,
  size: 0n,
  blocks: 0n,
  atimeMs: 1584961030299n,
  mtimeMs: 1582209885466n,
  ctimeMs: 1582209885466n,
  birthtimeMs: 1584961030299n,
  atimeNs: 1584961030299117000n,
  mtimeNs: 1582209885466684900n,
  ctimeNs: 1582209885466684900n,
  birthtimeNs: 1584961030299117000n,
  atime: 2020-03-23T10:57:10.299Z,
  mtime: 2020-02-20T14:44:45.466Z,
  ctime: 2020-02-20T14:44:45.466Z,
  birthtime: 2020-03-23T10:57:10.299Z
}
```

**参考：**[https://nodejs.org/api/fs.html#fs_fs_fstatsync_fd_options](https://nodejs.org/api/fs.html#fs_fs_fstatsync_fd_options)