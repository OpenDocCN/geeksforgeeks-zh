# Node.js `fs.utimes()`方法

> 原文: [https://www.geeksforgeeks.org/node-js-fs-utimes-method/](https://www.geeksforgeeks.org/node-js-fs-utimes-method/)

`fs.utimes()`方法用于异步更改文件的修改和访问时间戳。可以使用数字、字符串或日期对象来指定时间戳。如果时间戳无法转换为正确的数字，或者是 `NaN`、`Infinity` 或 `-Infinity`，则会引发错误。

## 语法

```js
fs.utimes( path, atime, mtime, callback )
```

## 参数

这个方法接受上面提到的和下面描述的四个参数：

*   `path`: 一个字符串，指示要更改时间戳的文件的路径。
*   `atime`: 要设置的新访问时间戳，是一个数字、字符串或 `Date` 对象。
*   `mtime`: 要设置的新修改时间戳，是一个数字、字符串或 `Date` 对象。
*   `callback`: 一个函数，当方法执行时将被调用。
    *   `err`: 如果方法失败，将抛出此错误。

下面的例子说明了 Node.js 中的 `fs.utimes()`方法：

## 例 1

```js
// Node.js program to demonstrate the
// fs.utimes() method

// Import the filesystem module
const fs = require('fs');

console.log("Details before changing time:");

// Get the stats object of the file
prevStats = fs.statSync("example_file.txt");

// Access the modified and access time of the file
console.log("Modification Time:", prevStats.mtime);
console.log("Access Time:", prevStats.atime);

// Get the current time to change the timestamps
let newModifiedTime = new Date();
let newAccessTime = new Date();

// Use the utimes() function to assign
// the new timestamps
fs.utimes(
  "example_file.txt",
  newAccessTime,
  newModifiedTime,
  () => {
    // Get the stats object of the file
    console.log("\nDetails after changing time:");

    // Get the stats object of the file
    changedStats = fs.statSync("example_file.txt");

    // Access the changed modified and
    // access time of the file
    console.log("Changed Modification Time:",
                 changedStats.mtime);

    console.log("Changed Access Time:",
                 changedStats.atime);
  }
);
```

**输出:**

```js
Details before changing time:
Modification Time: 2017-01-24T23:41:00.000Z
Access Time: 2018-02-26T00:05:00.000Z

Details after changing time:
Changed Modification Time: 2020-05-25T15:31:08.257Z
Changed Access Time: 2020-05-25T15:31:08.257Z
```

## 例 2

```js
// Node.js program to demonstrate the
// fs.utimes() method

// Import the filesystem module
const fs = require('fs');

console.log("Details before changing time:");

// Get the stats object of the file
prevStats = fs.statSync("example_file.txt");

// Access the modified and access time of the file
console.log("Modification Time:", prevStats.mtime);
console.log("Access Time:", prevStats.atime);

// Get the current time to change the timestamps
let newModifiedTime = new Date("January 25, 2017 05:11:00");
let newAccessTime = new Date("February 26, 2018 05:35:00");

// Use the utimes() function to assign
// the new timestamps
fs.utimes("example_file.txt", newAccessTime,
          newModifiedTime, () => {

  // Get the stats object of the file
  console.log("\nDetails after changing time:");

  // Get the stats object of the file
  changedStats = fs.statSync("example_file.txt");

  // Access the changed modified and
  // access time of the file
  console.log("Changed Modification Time:",
               changedStats.mtime);
  console.log("Changed Access Time:",
               changedStats.atime);
});
```

**输出:**

```js
Details before changing time:
Modification Time: 2015-12-20T19:42:00.000Z
Access Time: 2020-05-25T15:19:24.250Z

Details after changing time:
Changed Modification Time: 2017-01-24T23:41:00.000Z
Changed Access Time: 2018-02-26T00:05:00.000Z
```

## 参考

[https://nodejs.org/api/fs.html#fs_fs_utimes_path_atime_mtime_callback](https://nodejs.org/api/fs.html#fs_fs_utimes_path_atime_mtime_callback)