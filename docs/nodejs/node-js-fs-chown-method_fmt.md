# Node.js `fs.chown()`方法

> 原文：[https://www.geeksforgeeks.org/node-js-fs-chown-method/](https://www.geeksforgeeks.org/node-js-fs-chown-method/)

`fs.chown()`方法用于异步更改给定路径的所有者和组。该功能接受用户 id 和组 id，可用于设置各自的所有者和组。它有一个回调函数，如果函数失败，它会返回任何可能出现的错误。

## 语法

```js
fs.chown( path, uid, gid, callback )
```

## 参数

这个方法接受上面提到的和下面描述的四个参数：

*   `Path`：它是一个字符串、Buffer 或 URL，指示必须更改所有者和组的文件路径。
*   `uid`：一个数字，表示要设置的所有者对应的用户 id。
*   `Gid`：一个数字，表示要设置的组对应的组 ID。
*   `Callback`：一个函数，当方法执行时将被调用。
    *   `err`：如果方法失败，将抛出此错误。

下面的例子说明了 Node.js 中的 `fs.chown()`方法：

## 示例 1

本示例显示了所有者的设置。

```js
// Node.js program to demonstrate the
// fs.chown() method

// Import the filesystem module
const fs = require('fs');

let filepath = "example_file.txt";

// Set the owner to a new one keeping the group same
// New owner is "geeksforgeeks" with user id 1541
fs.chown(filepath, 1541, 999, (error) => {
  if (error)
    console.log("Error Code:", error);
  else
    console.log("uid and gid set successfully");
});
```

**运行代码前：**

```js
xubuntu@xubuntu: ~/Desktop/fs-chown$ ls -l
total 8
-rw-rw--w- 1 xubuntu xubuntu 4 Apr 25 04:08 example_file.txt
-rw-rw-r-- 1 xubuntu xubuntu 290 Apr 25 04:08 index.js
```

**代码输出：**

```js
Given uid and gid set successfully
```

**运行代码后：**

```js
xubuntu@xubuntu: ~/Desktop/fs-chown$ ls -l
total 8
-rw-rw--w- 1 geeksforgeeks xubuntu 4 Apr 25 04:08 example_file.txt
-rw-rw-r-- 1 xubuntu xubuntu 290 Apr 25 04:08 index.js
```

## 示例 2

此示例显示了组的设置。

```js
// Node.js program to demonstrate the
// fs.chown() method

// Import the filesystem module
const fs = require('fs');

let filepath = "example_file.txt";

// Set the owner and group both to a new one
// New owner is "sam" with owner id 1500
// New group is "author" with group id 1021
fs.chown(filepath, 1500, 1021, (error) => {
  if (error)
    console.log("Error Code:", error);
  else
    console.log("uid and gid set successfully");
});
```

**运行代码前：**

```js
xubuntu@xubuntu: ~/Desktop/fs-chown$ ls -l
total 8
-rw-rw--w- 1 xubuntu xubuntu 4 Apr 25 04:09 example_file.txt
-rw-rw-r-- 1 xubuntu xubuntu 290 Apr 25 04:09 index.js
```

**代码输出：**

```js
Given uid and gid set successfully
```

**运行代码后：**

```js
xubuntu@xubuntu: ~/Desktop/fs-chown$ ls -l
total 8
-rw-rw--w- 1 sam author 4 Apr 25 04:09 example_file.txt
-rw-rw-r-- 1 xubuntu xubuntu 290 Apr 25 04:09 index.js
```

## 参考

[https://nodejs.org/api/fs.html#fs_fs_chown_path_uid_gid_callback](https://nodejs.org/api/fs.html#fs_fs_chown_path_uid_gid_callback)