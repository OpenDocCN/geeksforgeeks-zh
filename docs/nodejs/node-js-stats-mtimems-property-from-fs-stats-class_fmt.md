# `stats.mtimeMs` 属性

> 原文：[https://www.geeksforgeeks.org/node-js-stats-mtimems-property-from-fs-stats-class/](https://www.geeksforgeeks.org/node-js-stats-mtimems-property-from-fs-stats-class/)

`stats.mtimeMs` 属性是 `fs` 模块内置的 `Stats` 类的一个属性，用于获取自 POSIX 纪元以来最后一次修改文件时的时间戳，以毫秒表示。

## 语法

```js
stats.mtimeMs;
```

## 参数

该属性不接受任何参数。

## 返回值

它返回一个数字或 `BigInt` 值，表示自 POSIX 纪元以来最后一次修改文件时的时间戳，以毫秒表示。

## 示例

以下示例说明了 `stats.mtimeMs` 属性在 Node.js 中的使用。

### 示例 1

```js
// Node.js program to demonstrate the
// stats.mtimeMs Property

// Accessing fs module
const fs = require('fs');

// Calling fs.Stats stats.mtimeMs
// property using stat
fs.stat('./', (err, stats) => {
    if (err) throw err;

    // The timestamp when the file
    // is last modified (in MS)
    console.log("Using stat: " + stats.mtimeMs);
});

// Using lstat
fs.lstat('./filename.txt', (err, stats) => {
    if (err) throw err;

    // The timestamp when the file
    // is last modified (in MS)
    console.log("Using lstat: "
            + stats.mtimeMs);
});
```

**输出：**

```js
Using stat: 1592665056784.809
Using lstat: 1592665183682.0176
```

### 示例 2

```js
// Node.js program to demonstrate the
// stats.mtimeMs Property

// Accessing fs module
const fs = require('fs').promises;

// Calling fs.Stats stats.mtimeMs
(async () => {
    const stats = await fs.stat('./filename.txt');

    // The timestamp when the file
    // is last modified (in MS)
    console.log("using stat synchronous: "
                + stats.mtimeMs);
})().catch(console.error)
```

**输出：**

```js
Using stat synchronous: 1592665183682.0176
```

## 注意

以上程序使用 `node filename.js` 命令编译运行，需正确使用 `file_path`。

## 参考资料

[https://nodejs.org/api/fs.html#fs_stats_mtimems](https://nodejs.org/api/fs.html#fs_stats_mtimems)