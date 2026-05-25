# Node.js util.types.isSetIterator()方法

> 原文：[https://www.geeksforgeeks.org/node-js-util-types-issetiterator-method/](https://www.geeksforgeeks.org/node-js-util-types-issetiterator-method/)

``util.types.isSetIterator()``方法是``util``模块的内置应用编程接口，主要是为了支持``Node.js``自身的内部API的需求而设计的。

该方法用于确定该值是否是为内置的``Set``实例返回的迭代器。

## 语法：

```js
util.types.isSetIterator( value )
```

## 参数：
该方法接受单个参数``value``，该值保存任何有效的JavaScript数据类型，如布尔、空、数字、对象等。

## 返回值：
它返回一个布尔值，即如果值是为内置``Set``实例返回的迭代器，则返回``true``，否则返回``false``。

下面的例子说明了在Node.js中使用``util.types.isSetIterator()``方法：

## 例 1：

```js
// Node.js program to demonstrate the
// util.types.isSetIterator() method

// Using require to access util module
const util = require('util');

// Using util.types.isSetIterator() method
console.log(util.types.isSetIterator(true));

// Using util.types.isSetIterator() method
console.log(util.types.isSetIterator(new Set().values()));

// Using util.types.isSetIterator() method
console.log(util.types.isSetIterator(new Set().keys()));
```

## 输出：

```js
false
true
true
```

## 例 2：

```js
// Node.js program to demonstrate the
// util.types.isSetIterator() method

// Using require to access util module
const util = require('util');

const set = new Set();

// Using util.types.isSetIterator() method
console.log(util.types.isSetIterator(set.keys()));

// Using util.types.isSetIterator() method
console.log(util.types.isSetIterator(set.entries()));

// Using util.types.isSetIterator() method
console.log(util.types.isSetIterator(set[Symbol.iterator]()));
```

## 输出：

```js
true
true
true
```

## 注意：
以上程序使用``node index.js``命令编译运行。

## 参考：
[https://nodejs.org/dist/latest-v13.x/docs/api/util.html#util_util_types_issetiterator_value](https://nodejs.org/dist/latest-v13.x/docs/api/util.html#util_util_types_issetiterator_value)