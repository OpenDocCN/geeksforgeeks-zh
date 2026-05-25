# Lodash _.cloneWith() 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-clonewith-method/](https://www.geeksforgeeks.org/lodash-_-clonewith-method/)

`Lodash` 是一个工作在 `underscore.js` 之上的 JavaScript 库，有助于处理数组、字符串、对象、数字等。

`_.cloneWith()` 方法与 `_.clone()` 方法相似，唯一不同的是它接受一个 `customizer`（定制器）。这个定制器会被调用以生成克隆值。如果此处使用的 `customizer` 返回 `undefined`，则克隆将改为由该方法处理。

**注意:** 这里用到的 `customizer` 最多可以用四个参数调用，分别是 `value`（值）、`index|key`（索引|键）、`object`（对象）、`stack`（栈）。

## 语法

```
_.cloneWith(value, [customizer])
```

## 参数

该方法接受两个参数：

*   `value`: 需要被克隆的值。
*   `customizer`: 用于自定义克隆过程的定制函数。

## 返回值

该方法返回克隆后的值。

## 示例 1

```javascript
// Requiring lodash library
const _ = require('lodash');

// Creating a function customizer
function customizer(val) {
  if (_.isElement(val)) {
    return val.cloneNode(false);
  }
}

// Defining value parameter
var value = [1, 2, 3];

// Calling cloneWith() method
var cloned_value = _.cloneWith(value, customizer);

// Displays output
console.log(cloned_value);
```

**输出:**

```
[ 1, 2, 3 ]
```

## 示例 2

```javascript
// Requiring lodash library
const _ = require('lodash');

// Creating a function customizer
function customizer(val) {
  if (_.isElement(val)) {
    return val.cloneNode(false);
  }
}

// Defining value parameter
var value = ['Geeks', 'for', 'Geeks'];

// Calling cloneWith() method
var cloned_value = _.cloneWith(value, customizer);

// Displays output
console.log(cloned_value);
```

**输出:**

```
[ 'Geeks', 'for', 'Geeks' ]
```

## 示例 3: 使用 `isInteger()` 方法作为 `customizer`

```javascript
// Requiring lodash library
const _ = require('lodash');

// Creating a function int which acts as
// customizer
function int(x) {
 if (_.isInteger(x)) {
   return true;
   }
}

// Calling cloneWith() method along with
// its parameter
var cloned_value = _.cloneWith({ gfg: 5,
        geeksforgeeks: 6}, int);

// Displays output
console.log(cloned_value);
```

**输出:**

```
{ gfg: 5, geeksforgeeks: 6 }
```

**参考:** [https://lodash.com/docs/4.17.15#cloneWith](https://lodash.com/docs/4.17.15#cloneWith)