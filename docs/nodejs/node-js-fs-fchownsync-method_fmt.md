# Node.js | fs.fchownSync()方法

> 原文: [https://www.geeksforgeeks.org/node-js-fs-fchownsync-method/](https://www.geeksforgeeks.org/node-js-fs-fchownsync-method/)

`fs.fchownSync()`方法用于同步更改给定文件描述符的所有者和组。该功能接受用户 id 和组 id，可用于设置各自的所有者和组。它不返回任何东西。

## 语法:

```js
fs.fchownSync( fd, uid, gid )
```

## 参数:

该方法接受三个参数，如上所述，如下所述:

*   `fd`: 是一个整数，表示需要更改所有者和组的文件的文件描述符。
*   `uid`: 是一个数字，表示要设置的所有者对应的用户 id。
*   `gid`: 是一个数字，表示要设置的组对应的组 ID。

下面的例子说明了 Node.js 中的 `fs.fchownSync()`方法:

## 示例

### 示例 1

本示例显示了所有者的设置。

```js
// Node.js program to demonstrate the
// fs.fchownSync() method

// Import the filesystem module
const fs = require('fs');

// Get the file descriptor for the file
let fd = fs.openSync("example_file.txt", "r");

// Set the owner to a new one keeping the group same
// New owner is "geeksforgeeks" with user id 1010
// The old group is "xubuntu" with group id 999
fs.fchownSync(fd, 1010, 999);
console.log("uid and gid set successfully");
```

**运行代码前:**

```js
xubuntu@xubuntu: ~/Desktop/fs-fchownSync$ ls -l
total 8
-rw-rw--w- 1 xubuntu xubuntu 4 Apr 22 09:10 example_file.txt
-rw-rw-r-- 1 xubuntu xubuntu 290 Apr 22 09:15 index.js
```

**代码输出:**

```js
Given uid and gid set successfully
```

**运行代码后:**

```js
xubuntu@xubuntu: ~/Desktop/fs-fchownSync$ ls -l
total 8
-rw-rw--w- 1 geeksforgeeks xubuntu 4 Apr 22 09:10 example_file.txt
-rw-rw-r-- 1 xubuntu xubuntu 290 Apr 22 09:15 index.js
```

### 示例 2

此示例显示了组的设置。

```js
// Node.js program to demonstrate the
// fs.fchownSync() method

// Import the filesystem module
const fs = require('fs');

// Get the file descriptor for the file
let fd = fs.openSync("example_file.txt", "r");

// Set the group to a new one keeping the owner same
// The old owner is "xubuntu" with user id 999
// New group is "author" with group id 1015
fs.fchownSync(fd, 999, 1015);
console.log("uid and gid set successfully");
```

**运行代码前:**

```js
xubuntu@xubuntu: ~/Desktop/fs-fchownSync$ ls -l
total 8
-rw-rw--w- 1 xubuntu xubuntu 4 Apr 22 09:10 example_file.txt
-rw-rw-r-- 1 xubuntu xubuntu 290 Apr 22 09:15 index.js
```

**代码输出:**

```js
Given uid and gid set successfully
```

**运行代码后:**

```js
xubuntu@xubuntu: ~/Desktop/fs-fchownSync$ ls -l
total 8
-rw-rw--w- 1 xubuntu author 4 Apr 22 09:10 example_file.txt
-rw-rw-r-- 1 xubuntu xubuntu 290 Apr 22 09:15 index.js
```

## 参考

[https://nodejs.org/api/fs.html#fs_fs_fchownsync_fd_uid_gid](https://nodejs.org/api/fs.html#fs_fs_fchownsync_fd_uid_gid)