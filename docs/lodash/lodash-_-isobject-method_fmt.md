# Lodash _.isObject() 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-isobject-method/](https://www.geeksforgeeks.org/lodash-_-isobject-method/)

`Lodash` 是一个工作在 `underscore.js` 之上的 JavaScript 库，有助于处理数组、字符串、对象、数字等。

`_.isObject()` 方法用于查找给定值是否为对象。如果给定值参数是一个对象，则返回布尔值 `true`，否则返回 `false`。

**语法:**

```javascript
_.isObject(value)
```

**参数:** 该方法接受如上所述的单个参数，如下所述:

*   `value`: 该参数保存要检查的值。

**返回值:** 如果值是一个对象，这个方法返回 `true`，否则返回 `false`。

**示例 1:** 这里，`const _ = require('lodash')` 用于将 `lodash` 库导入文件。

## Javascript

```javascript
// Requiring the lodash library
const _ = require("lodash");

// Use of _.isObject() method
console.log(_.isObject('GeeksforGeeks'));
console.log(_.isObject(1));
console.log(_.isObject([1, 2, 3]));
```

**输出:**

```text
false
false
true
```

**示例 2:**

## Javascript

```javascript
// Requiring the lodash library
const _ = require("lodash");

// Use of _.isObject() method
console.log(_.isObject({}));
console.log(_.isObject(null));
console.log(_.isObject(_.noop));
```

**输出:**

```text
true
false
true
```