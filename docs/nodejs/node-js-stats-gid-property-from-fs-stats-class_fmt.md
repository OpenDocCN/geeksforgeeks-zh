# Node.js 中来自 fs.Stats 类的 gid 属性

> 原文：[https://www.geeksforgeeks.org/node-js-stats-gid-property-from-fs-stats-class/](https://www.geeksforgeeks.org/node-js-stats-gid-property-from-fs-stats-class/)

## 概述

`stats.gid` 属性是 `fs` 内置模块中 `Stats` 类的一个属性，用于获取文件所属组的数字（`number` 或 `bigint`）标识。

## 语法

```js
stats.gid;
```

## 返回值

它返回一个数字或 `BigInt` 值，代表拥有该文件的组的身份。

## 示例

下面的例子说明了 `stats.gid` 属性在 Node.js 中的使用：

### 示例 1

```js
// Node.js program to demonstrate the   
// stats.gid property

// Accessing fs module
const fs = require('fs');

// Calling fs.Stats stats.gid
// for directory using stat
fs.stat('./', (err, stats) => {
    if (err) throw err;
    console.log("using stat: numeric "
        + "identity of the group is "
        + stats.gid);
});

// Using lstat
fs.lstat('./', (err, stats) => {
    if (err) throw err;
    console.log("using lstat: numeric "
        + "identity of the group is "
        + stats.gid);
});

// For file
// Using stat
fs.stat('./filename.txt', (err, stats) => {
    if (err) throw err;
    console.log("using stat: numeric "
        + "identity of the group is "
        + stats.gid);
});

// Using lstat
fs.lstat('./filename.txt', (err, stats) => {
    if (err) throw err;
    console.log("using lstat: numeric "
        + "identity of the group is "
        + stats.gid);
});
```

**输出：**

```js
using stat: numeric identity of the group is  5687
using lstat: numeric identity of the group is  5687
using stat: numeric identity of the group is  5687
using lstat: numeric identity of the group is  5687
```

### 示例 2

```js
// Node.js program to demonstrate the   
// stats.gid property

// Accessing fs module
const fs = require('fs').promises;

// Calling fs.Stats stats.gid
(async () => {
    const stats = await fs.stat('./filename.txt');
    console.log("using stat synchronous: numeric"
        + " identity of the group is  " + stats.gid);
})().catch(console.error)
```

**输出：**

```js
(node:15204) ExperimentalWarning: The fs.promises API 
is experimental 
using stat synchronous: numeric identity of the group is 5687
```

## 注意事项

以上程序使用 `node filename.js` 命令编译运行，需正确使用 `file_path`。该 API 将在 POSIX 系统中正常工作。在像 Windows 这样的其他系统中，它将返回 `0`。

## 参考资料

[https://nodejs.org/api/fs.html#fs_stats_gid](https://nodejs.org/api/fs.html#fs_stats_gid)