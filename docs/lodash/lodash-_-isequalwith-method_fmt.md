# Lodash _.isEqualWith() 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-isequalwith-method/](https://www.geeksforgeeks.org/lodash-_-isequalwith-method/)

**Lodash** 是一个工作在 Underscore.js 之上的 JavaScript 库，有助于处理数组、字符串、对象、数字等。

`_.isEqualWith()` 方法与 `_.isEqual()` 方法相似，唯一不同的是它接受一个 `customizer`，调用这个定制器是为了比较值。此外，如果此处使用的 `customizer` 返回 `undefined`，则会通过默认方法来处理比较。

**注意：** 这里使用的 `customizer` 最多可以用 6 个参数调用，分别是 `objValue`、`othValue`、`index` | `key`、`object`、`other`、`stack`。

## 语法

```
_.isEqualWith(value, other, [customizer])
```

## 参数

该方法接受三个参数，如下所述：

*   `value`: 要比较的值。
*   `other`: 另一个要比较的值。
*   `customizer`: 用于自定义比较的函数。

## 返回值

如果所述值相等，则该方法返回 `true`，否则返回 `false`。

## 示例 1

```javascript
// Requiring lodash library
const _ = require('lodash');

// Defining a function portal
function portal(val) {
  return /^G(?:fG|eeksforGeeks)$/.test(val);
}

// Defining customizer to compare values
function customizer(objectValue, otherValue) {
  if (portal(objectValue) && portal(otherValue)) {
    return true;
  }
}

// Initializing values
var val = ['GeeksforGeeks', 'CS-portal'];
var otherval = ['GfG', 'CS-portal'];

// Calling isEqualWith() method with all
// its parameter
let result = _.isEqualWith(val, otherval, customizer);

// Displays output
console.log(result);
```

**输出：**

```
true
```

## 示例 2

```javascript
// Requiring lodash library
const _ = require('lodash');

// Defining a function portal
function portal(val) {
  return /^G(?:fG|eeksforGeeks)$/.test(val);
}

// Defining customizer to compare values
function customizer(objectValue, otherValue) {
  if (portal(objectValue) && portal(otherValue)) {
    return true;
  }
}

// Initializing values
var val = ['GeeksforGeeks', 'CS-portal'];
var otherval = ['GfG', 'portal'];

// Calling isEqualWith() method with all
// its parameter
let result = _.isEqualWith(val, otherval, customizer);

// Displays output
console.log(result);
```

**输出：**

```
false
```

## 示例 3

```javascript
// Requiring lodash library
const _ = require('lodash');

// Defining a function gfg
function gfg(val) {
  return val;
}

// Defining customizer
function intg(x, y) {
 if (gfg(x) === gfg(y)){  
  return true;
   }
}

// Calling isEqualWith() method with all
// its parameter
let result = _.isEqualWith('gf', 'gfg', intg);

// Displays output
console.log(result);
```

**输出：**

```
false
```

## 参考资料

[https://lodash.com/docs/4.17.15#isEqualWith](https://lodash.com/docs/4.17.15#isEqualWith)