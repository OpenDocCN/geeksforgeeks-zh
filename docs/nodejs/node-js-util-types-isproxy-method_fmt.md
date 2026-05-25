# Node.js util.types.isProxy()方法

> 原文：`https://www.geeksforgeeks.org/node-js-util-types-isproxy-method/`

`util.types.isProxy()`方法是`util`模块的内置应用编程接口，主要是为了支持Node.js自身内部API的需求而设计的。`util.types.isProxy()`方法用于检查给定值是否是代理实例。

## 语法：
```js
util.types.isProxy( value )
```

## 参数：
该函数接受如上所述的单个参数，如下所述：

*   `value`：需要检查是否为代理实例的值。

## 返回值：
如果传递的值是代理，则返回布尔值，即`true`，否则返回`false`。

下面的程序说明了`util.types.isProxy()`方法：

## 例 1：
```js
// Node.js program to demonstrate the
// util.types.isProxy() method

// Import the util module
const util = require('util');

// Creating a target
const target = {};

// Checking the proxy instance
let proxyObj = new Proxy(target, {});
console.log(proxyObj);

isProxy = util.types.isProxy(proxyObj);
console.log("Object is a proxy instance:", isProxy);

// Checking a normal object
normalObj = {a: "1", b: "2"};
console.log(normalObj);

isProxy = util.types.isProxy(normalObj);
console.log("Object is a proxy instance:", isProxy);
```

## 输出：
```js
{}
Object is a proxy instance: true
{ a: '1', b: '2' }
Object is a proxy instance: false
```

## 例 2：
```js
// Node.js program to demonstrate the
// util.types.isProxy() method

// Import the util module
const util = require('util');

// Creating a target
const target = {};

// Checking the proxy object
console.log("Object is a proxy instance:");
console.log(util.types.isProxy(new Proxy(target, {})));

// Checking a normal object
console.log("Object is a proxy instance:");
console.log(util.types.isProxy(new Object()));
```

## 输出：
```js
Object is a proxy instance:
true
Object is a proxy instance:
false
```

## 参考：
`https://nodejs.org/api/util.html#util_util_types_isproxy_value`