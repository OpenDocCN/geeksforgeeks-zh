# util.types.isArgumentsObject() 方法

> 原文：[https://www.geeksforgeeks.org/node-js-util-types-isargumentsobject-method/](https://www.geeksforgeeks.org/node-js-util-types-isargumentsobject-method/)

`util.types.isArgumentsObject()` 方法是 `util` 模块的内置 API，主要是为了支持 Node.js 自身内部 API 的需求而设计的。
`util.types.isArgumentsObject()` 方法用于检查给定值是否是参数对象。

## 语法

```js
util.types.isArgumentsObject( value )
```

## 参数

该函数接受一个参数，如下所述：

*   `value`：要为参数对象检查的值。

## 返回值

如果传递的值是参数对象，则返回布尔值，即 `true`，否则返回 `false`。

下面的程序说明了 Node.js 中的 `util.types.isArgumentsObject()` 方法：

## 示例 1

```js
// Node.js program to demonstrate the
// util.types.isArgumentsObject() method

// Import the util module
const util = require('util');

// Checking the arguments object
console.log(util.types.isArgumentsObject(arguments));

// Checking new object created by the constructor
console.log(util.types.isArgumentsObject(new Object()));

// Checking a normal object
console.log(util.types.isArgumentsObject(
            {arg1: "Hello", arg2: "World"}));
```

**输出：**

```js
true
false
false
```

## 示例 2

```js
// Node.js program to demonstrate the
// util.types.isArgumentsObject() method

// Import the util module
const util = require('util');

function exampleFn(arg1, arg2) {

  // Checking the arguments object
  let argumentsObj = arguments;
  console.log(arguments);

  isArgumentObj = util.types.isArgumentsObject(argumentsObj);
  console.log("Object is arguments object:", isArgumentObj);

  // Checking a normal object
  let normalObj = {arg1: "hello", arg2: "world"};
  console.log(normalObj);

  isArgumentObj = util.types.isArgumentsObject(normalObj);
  console.log("Object is arguments object:", isArgumentObj);
}

exampleFn('hello', 'world');
```

**输出：**

```js
[Arguments] { '0': 'hello', '1': 'world' }
Object is arguments object: true
{ arg1: 'hello', arg2: 'world' }
Object is arguments object: false
```

**参考：** [https://nodejs.org/api/util.html#util_util_types_isargumentsobject_value](https://nodejs.org/api/util.html#util_util_types_isargumentsobject_value)