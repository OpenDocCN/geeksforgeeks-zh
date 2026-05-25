# Node.js `process.stderr.fd` 属性

> 原文: [https://www.geeksforgeeks.org/node-js-process-stderr-fd-property/](https://www.geeksforgeeks.org/node-js-process-stderr-fd-property/)

`process.stderr.fd` 是 `process` 模块内 `Process` 类的内置应用编程接口，用于返回 `process.stderr` 的底层文件描述符的值。

**语法:**

```js
const process.stderr.fd
```

**参数:** 该 API 不接受任何参数作为参数。

**返回值:** 这个 API 返回 `process.stderr` 的底层文件描述符的值。

**例 1:**

## `index.js`

```js
// Node.js program to demonstrate the
// process.stderr.fd

// Importing process module
const process = require('process');

// Getting the value of file descriptor
// by using process.stderr.fd
const value = process.stderr.fd

// Display the result
console.log(value)
```

使用以下命令运行 `index.js` 文件:

```js
node index.js
```

**输出:**

```js

```

**例 2:**

## `index.js`

```js
// Node.js program to demonstrate the
// process.stderr.fd

// Importing process module
const process = require('process');

// Updating file descriptor value
process.stderr.fd = 10

// Getting the value of file descriptor
// by using process.stderr.fd
const value = process.stderr.fd

// Display the result
console.log(value)
```

使用以下命令运行 `index.js` 文件:

```js
node index.js
```

**输出:**

```js

```

**参考:** [https://nodejs.org/dist/latest-v16.x/docs/api/process.html#process_process_stderr_fd](https://nodejs.org/dist/latest-v16.x/docs/api/process.html#process_process_stderr_fd)