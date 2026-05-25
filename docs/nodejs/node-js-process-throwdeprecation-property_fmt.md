# Node.js process.throwDeprecation Property

> 原文: [https://www.geeksforgeeks.org/node-js-process-throwdeprecation-property/](https://www.geeksforgeeks.org/node-js-process-throwdeprecation-property/)

`process.throwDeprecation` 属性是 `process` 模块的内置 API，用于指示当前 Node.js 进程是否设置了 `--throw-deprecation` 标志。`process.throwDeprecation` 是可变的，因此在运行时，是否会因为拒绝警告而导致错误可能会改变。

**语法:**

```js
process.throwDeprecation
```

**返回值:** 该属性表示当前 Node.js 进程是否设置了 `--throw-deprecation` 标志。

下面的例子说明了在 Node.js 中 `process.throwDeprecation` 的使用。

### 例 1:

```js
// Node.js program to demonstrate the
// process.throwDeprecation Property

// Include process module
const process = require('process');

// Printing process.throwDeprecation
// property value
console.log(process.throwDeprecation);
```

**运行命令:** `node --throw-deprecation hello.js`

**输出 1:**

```js
true
```

**运行命令:** `node hello.js`

**输出 2:**

```js
undefined
```

### 例 2:

```js
// Node.js program to demonstrate the
// process.throwDeprecation Property

// Include process module
const process = require('process');

// Instance Properties
process.throwDeprecation = false;

// Printing process.throwDeprecation
// property value
console.log(process.throwDeprecation);

// Instance Properties
process.throwDeprecation = true;

// Printing process.throwDeprecation
// property value
console.log(process.throwDeprecation);
```

**运行命令:** `node --throw-deprecation hello.js`

**输出 1:**

```js
true
true
```

**运行命令:** `node hello.js`

**输出 2:**

```js
false
true
```

**参考:** [https://nodejs.org/api/process.html#process_process_throwdeprecation](https://nodejs.org/api/process.html#process_process_throwdeprecation)