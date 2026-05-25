# Node.js util.types.isMapIterator()方法

> 原文：[https://www.geeksforgeeks.org/node-js-util-types-ismapiterator-method/](https://www.geeksforgeeks.org/node-js-util-types-ismapiterator-method/)

`util.types.isMapIterator()`方法是`util`模块的内置应用编程接口，主要设计用于支持`Node.js`内部API的需求。

方法用于确定该值是否是为内置的[映射](https://www.geeksforgeeks.org/map-in-javascript/)实例返回的迭代器。

**语法：**

```js
util.types.isMapIterator( value )
```

**参数：** 该方法接受单个参数`value`，该值保存任何有效的JavaScript数据类型，如布尔、空、数字、对象等。

**返回值：** 返回布尔值，即如果值是为内置`Map`返回的迭代器，则返回`true`，否则返回`false`。

下面的例子说明了在Node.js中使用`util.types.isMapIterator()`方法：

**例1：**

```js
// Node.js program to demonstrate the
// util.types.isMapIterator() method

// Using require to access util module
const util = require('util');

// Using util.types.isMapIterator() method
console.log(util.types.isMapIterator(true));

// Using util.types.isMapIterator() method
console.log(util.types.isMapIterator(new Map().values()));

// Using util.types.isMapIterator() method
console.log(util.types.isMapIterator(new Map().keys()));
```

**输出：**

```js
false
true
true
```

**例2：**

```js
// Node.js program to demonstrate the
// util.types.isMapIterator() method

// Using require to access util module
const util = require('util');

const map = new Map();

// Using util.types.isMapIterator() method
console.log(util.types.isMapIterator(map.keys()));

// Using util.types.isMapIterator() method
console.log(util.types.isMapIterator(map.entries()));

// Using util.types.isMapIterator() method
console.log(util.types.isMapIterator(map[Symbol.iterator]()));
```

**输出：**

```js
true
true
true
```

**注意：** 以上程序使用`node index.js`命令编译运行。

**参考：** [https://nodejs.org/dist/latest-v13.x/docs/api/util.html#util_util_types_ismapiterator_value](https://nodejs.org/dist/latest-v13.x/docs/api/util.html#util_util_types_ismapiterator_value)