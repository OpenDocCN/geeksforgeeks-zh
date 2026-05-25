# Node.js process.pid 属性

> 原文: [https://www.geeksforgeeks.org/node-js-process-pid-property/](https://www.geeksforgeeks.org/node-js-process-pid-property/)

`process pid` 属性是 `process` 模块的内置应用编程接口，用于获取进程的 PID。

## 语法:

```js
process.pid
```

## 返回值:
该属性返回一个指定进程 PID 的整数值。

下面的例子说明了在 Node.js 中 `process pid` 属性的使用:

## 示例:

```js
// Node.js program to demonstrate the
// process.pid Property

// Include process module
const process = require('process');

// Printing process.pid property value
console.log("process id is " + process.pid);
```

## 输出:

```js
process id is 11436
```

## 注意:
以上程序使用 `node filename.js` 命令编译运行。

## 参考:
[https://nodejs.org/api/process.html#process_process_pid](https://nodejs.org/api/process.html#process_process_pid)