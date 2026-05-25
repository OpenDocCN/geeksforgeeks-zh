# Node.js 中 `fs.Stats.uid` 属性

> 原文：[https://www.geeksforgeeks.org/node-js-stats-uid-property-from-fs-stats-class/](https://www.geeksforgeeks.org/node-js-stats-uid-property-from-fs-stats-class/)

`stats.uid` 属性是 `fs` 内置模块中 `Stats` 类的一部分，用于获取文件所属用户的数字（`number` 或 `bigint`）标识。

## 语法

```js
stats.uid;
```

## 返回值

它返回一个数字或 `BigInt` 值，代表拥有该文件的用户的身份。

下面的例子说明了 `stats.uid` 属性在 Node.js 中的使用：

## 示例 1

```js
// Node.js program to demonstrate the
// stats.uid property

// Accessing fs module
const fs = require('fs');

// Calling fs.Stats stats.uid
//for directory using stat
fs.stat('./', (err, stats) => {
  if (err) throw err;
  console.log("using stat: numeric "
    + "identity of the user is "
    + stats.uid);
});

//using lstat
fs.lstat('./', (err, stats) => {
  if (err) throw err;
  console.log("using lstat: numeric "
    + "identity of the user is "
    + stats.uid);
});

// For file
// Using stat
fs.stat('./filename.txt', (err, stats) => {
  if (err) throw err;
  console.log("using stat: numeric "
    + "identity of the user is "
    + stats.uid);
});

// Using lstat
fs.lstat('./filename.txt', (err, stats) => {
  if (err) throw err;
  console.log("using lstat: numeric identity"
    + " of the user is  "+stats.uid);
});
```

输出：

```js
using stat: numeric identity of the user is  9932440
using lstat: numeric identity of the user is  9932440
using stat: numeric identity of the user is  9932440
using lstat: numeric identity of the user is  9932440
```

## 示例 2

```js
// Node.js program to demonstrate the
// stats.uid property

// Accessing fs module
const fs = require('fs').promises;

// Calling fs.Stats stats.uid
(async() => {
    const stats = await fs.stat('./filename.txt');
  console.log("using stat synchronous: numeric "
    + "identity of the user is  "+stats.uid);
})().catch(console.error)
```

输出：

```js
(node:14456) ExperimentalWarning: The fs.promises API
is experimental
using stat synchronous: numeric identity of the user is 9932440
```

## 注意事项

以上程序使用 `node filename.js` 命令编译运行，需正确使用 `file_path`。该 API 将在 `POSIX` 系统中正常工作。在像 `WINDOWS` 这样的其他系统中，它将返回 `0`。

## 参考资料

[https://nodejs.org/api/fs.html#fs_stats_uid](https://nodejs.org/api/fs.html#fs_stats_uid)