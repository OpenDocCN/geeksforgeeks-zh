# Node.js util.types.isRegExp()方法

> 原文：`https://www.geeksforgeeks.org/node-js-util-types-isregexp-method/`

`util`模块的`util.types.isRegExp()`方法，主要是为了支持Node.js自带的内部API的需求而设计的。用于检查传递的值是否为正则表达式。

## 语法

```js
util.types.isRegExp( value )
```

## 参数

该方法接受单个参数`value`，该值保存任何值，即任何模块的实例。

## 返回值

如果传递的值是正则表达式，该方法返回一个布尔值，即`true`，否则返回`false`。

下面的例子说明了`util.types.isRegExp()`方法在Node.js中的使用：

## 例1

```js
// Node.js program to demonstrate the   
// util.types.isRegExp() method

// It includes util module
const util = require('util');

// Returns false as the passed instance
// is not regular expression
console.log(util.types.isRegExp(new Map()));

// Returns true as the passed instance
// is regular expression
console.log(util.types.isRegExp(new RegExp('xyz')));
```

## 输出

```js
false
true
```

## 例2

```js
// Node.js program to demonstrate the   
// util.types.isRegExp() method

// It includes util module
const util = require('util');

// Returns false as the passed instance
// is not regular expression
console.log(util.types.isRegExp(new Map()));

// Returns true as the passed instance
// is regular expression
console.log(util.types.isRegExp(new RegExp('xyz')));

// Returns true as the passed instance
// is regular expression
console.log(util.types.isRegExp(/abc/));

// Returns false as the passed instance
// is not regular expression
console.log(util.types.isRegExp(new Int32Array()));

// Returns true as the passed instance
// is regular expression 
console.log(util.types.isRegExp(/ab+c/));
```

## 输出

```js
false
true
true
false
true
```

## 参考

`https://nodejs.org/api/util.html#util_util_types_isregexp_value`