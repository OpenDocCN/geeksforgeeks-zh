# Lodash _.extendWith() 方法

> 原文：[https://www.geeksforgeeks.org/lodash-_-extendwith-method/](https://www.geeksforgeeks.org/lodash-_-extendwith-method/)

`Lodash` 是一个工作在 `underscore.js` 之上的 JavaScript 库，有助于处理数组、字符串、对象、数字等。

`_.extendWith()` 方法与 `_.assignIn()` 方法相似，唯一的区别是它接受一个 `customizer`，调用这个 `customizer` 是为了生成赋值。此外，如果此处使用的 `customizer` 返回 `undefined`，则该赋值改为由该方法处理。

**注：**

*   此处使用的 `customizer` 可以接受五个参数，分别是 `objValue`、`srcValue`、`key`、`object` 和 `source`。
*   此处使用的对象会以这种方式被修改。

**语法：**

```javascript
_.extendWith(object, sources, [customizer])
```

**参数：** 该方法接受三个参数，如下所述：

*   `object`：目标对象。
*   `source`：源对象。
*   `customizer`：自定义赋值的函数。

**返回值：** 这个方法返回一个对象。

**例 1：**

```javascript
// Requiring lodash library
const _ = require('lodash');

// Defining a function customizer
function customizer(objectVal, sourceVal) {
  return _.isUndefined(objectVal) ? 
        sourceVal : objectVal;
}

// Calling extendWith method with its parameter
let obj = _.extendWith({ 'gfg': 1 }, 
        { 'geek': 3 }, customizer);

// Displays output
console.log(obj);
```

**输出：**

```javascript
{ gfg: 1, geek: 3 }
```

**例 2：**

```javascript
// Requiring lodash library
const _ = require('lodash');

// Defining a function customizer
function customizer(objectVal, sourceVal) {
  return _.isUndefined(objectVal) ? 
        sourceVal : objectVal;
}

// Defining a function GfG
function GfG() {
  this.p = 7;
}

// Defining a function Portal
function Portal() {
  this.r = 9;
}

// Defining prototype of above functions
GfG.prototype.q = 8;
Portal.prototype.s = 10;

// Calling extendWith method
// with its parameter
let obj = _.extendWith({ 'p': 6 }, 
    new GfG, new Portal, customizer);

// Displays output
console.log(obj);
```

**输出：**

```javascript
{ p: 6, q: 8, r: 9, s: 10 }
```

**参考：** [https://lodash.com/docs/4.17.15#assignInWith](https://lodash.com/docs/4.17.15#assignInWith)