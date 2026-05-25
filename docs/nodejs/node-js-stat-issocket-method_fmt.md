# Node.js `stats.isSocket()` 方法

> 原文：[https://www.geeksforgeeks.org/node-js-stat-issocket-method/](https://www.geeksforgeeks.org/node-js-stat-issocket-method/)

`stats.isSocket()` 方法是 `fs` 内置模块的应用编程接口（API）。用于检查 `fs.Stats` 对象是否描述了一个套接字。

## 语法

```js
stats.isSocket();
```

## 参数

此方法不接受任何参数。

## 返回值

此方法返回一个布尔值。如果 `fs.Stats` 对象描述的是一个套接字，则返回 `true`，否则返回 `false`。

下面的例子说明了 `stats.isSocket()` 方法在 Node.js 中的使用：

## 例 1

```js
// Node.js program to demonstrate the
// stat.isSocket() Method

// Accessing fs module
const fs = require('fs');

// Calling isSocket() method from fs.Stats
// class using lstat() method
fs.lstat('./', (err, stats) => {
    if (err) throw err;

    // console.log(`stats: ${JSON.stringify(stats)}`);
    console.log(stats.isSocket());
    if (stats.isSocket()) {
        console.log("fs.lstats describes a Socket.");
    } else {
        console.log("fs.lstats does not describe a socket.");
    }
});

// Using stat() method
fs.stat('./', (err, stats) => {
    if (err) throw err;

    // console.log(`stats: ${JSON.stringify(stats)}`);
    console.log(stats.isSocket());
    if (stats.isSocket()) {
        console.log("fs.stats describes a socket.");
    } else {
        console.log("fs.stats does not describe a socket.");
    }
});
```

## 输出

```js
false
fs.lstats does not describe a socket.
false
fs.stats does not describe a socket.
```

## 例 2

```js
// Node.js program to demonstrate the
// stat.isSocket() Method

// Accessing fs module
const fs = require('fs').promises;

// Calling isSocket() method from
// fs.Stats class
(async () => {
    const stat = await fs.lstat('./');
    console.log(stat.isSocket());
})().catch(console.error)
```

## 输出

```js
false
```

## 注意

以上程序使用 `node filename.js` 命令编译运行，需正确使用 `file_path`。

## 参考资料

[https://nodejs.org/api/fs.html#fs_stats_issocket](https://nodejs.org/api/fs.html#fs_stats_issocket)