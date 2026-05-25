# Node.js process.version 属性

> 原文: [https://www.geeksforgeeks.org/node-js-process-version-property/](https://www.geeksforgeeks.org/node-js-process-version-property/)

`process.version`属性是`process`模块的内置应用编程接口，用于检查 node.js 版本。

## 语法:

```js
process.version
```

## 返回:
返回一个表示 Node.js 版本的字符串

下面的例子说明了在 Node.js 中`process.version`属性的使用:

## 例 1:

```js
// Allocating process module
const process = require('process');

// Printing process.version
console.log("node.js version " + process.version);
```

## 输出:

```js
node.js version v10.16.0
```

## 例 2:

```js
// Allocating process module
const process = require('process');

// Printing process.version
const ver = process.version;
console.log("node.js version " + ver);

// Printing version name
var name = "";

if(ver.startsWith('v10.')) {
        name = 'Dubnium';
}else if(ver.startsWith('v8.')) {
    name = 'Caron';
}else if(ver.startsWith('v6.')) {
    name = 'Boron';
}else if(ver.startsWith('v4.')) {
    name = 'Argon';
}else {
    name = 'unknown';
}
console.log("Node.js version name: " + name);
```

## 输出:

```js
node.js version v10.16.0
Node.js version name: Dubnium
```

参考: [https://nodejs.org/api/process.html#process_process_version](https://nodejs.org/api/process.html#process_process_version)