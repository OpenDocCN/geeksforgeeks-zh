# Node.js `process.connected` 属性

> 原文: [https://www.geeksforgeeks.org/node-js-process-connected-property/](https://www.geeksforgeeks.org/node-js-process-connected-property/)

`process.connected` 属性是 `process` 模块的一个内置属性，子进程使用它来检查它是否连接到父进程。

**语法:**

```js
process.connected
```

**返回值:** 如果该进程是由另一个进程产生的，并且这两个进程是连接的，那么 `process.connected` 属性将返回 `true`；如果它们断开连接，则返回 `false`。

**示例 1:** 如果进程已连接，则 `process.connected` 将返回 `true`。

## 父进程 (Parent.js)

```js
// Require fork method from child_process 
// to spawn child process
const fork = require('child_process').fork;

// Child process file
const child_file = 'Child.js';

// Spawn child process
const child = fork(child_file);
```

## 子进程 (Child.js)

```js
console.log('In Child.js')

// If it is connected
if (process.connected) {

    // Print messages
    console.log("Child.js is connected");
} else {

    // Print messages
    console.log("Child.js is disconnected");
}
```

使用以下命令运行 `Parent.js` 文件:

```bash
node Parent.js
```

**输出:**

```text
In Child.js
Child.js is connected
```

**示例 2:** 如果进程断开，则 `process.connected` 将返回 `false`。

## 父进程 (Parent.js)

```js
// Require fork method from child_process 
// to spawn child process
const fork = require('child_process').fork;

// Child process file
const child_file = 'Child.js';

// Spawn child process
const child = fork(child_file);
```

## 子进程 (Child.js)

```js
console.log('In Child.js')

// Disconnect the process
process.disconnect();

// If it is connected
if (process.connected) {

    // Print messages
    console.log("Child.js is connected");
} else {

    // Print messages
    console.log("Child.js is disconnected");
}
```

使用以下命令运行 `Parent.js` 文件:

```bash
node Parent.js
```

**输出:**

```text
In Child.js
Child.js is disconnected
```

**参考:** [https://nodejs.org/api/process.html#process_process_connected](https://nodejs.org/api/process.html#process_process_connected)