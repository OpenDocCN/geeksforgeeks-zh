# Lodash `_.defaultTo()` 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-defaultto-method/](https://www.geeksforgeeks.org/lodash-_-defaultto-method/)

Lodash 是一个工作在下划线之上的 JavaScript 库。Lodash 有助于处理数组、字符串、对象、数字等。

`_.defaultTo()` 方法用于检查给定的 `value`，并确定是否应该恢复默认值。当值为 `NaN`、`null` 或 `undefined` 时，返回 `defaultValue` 参数中给出的值。

## 语法

```
_.defaultTo( value, defaultValue )
```

## 参数

该方法接受两个参数，如上所述，如下所述:
* `value`: 该参数保存要检查的值。
* `defaultValue`: 此参数保存要恢复的默认值。

## 返回值

该方法返回解析值。

### 示例 1

```javascript
// Requiring the lodash library
const _ = require("lodash");

// Return the resolved value
// by _.defaultTo() method
console.log(_.defaultTo(5, 15));

// Return the resolved value
// by _.defaultTo() method
console.log(_.defaultTo(82, 43));
```

**输出:**

```
5
82
```

### 示例 2

```javascript
// Requiring the lodash library
const _ = require("lodash");

// When the value is NaN, defaultValue
// is returned by _.defaultTo() method
console.log(_.defaultTo(null, 15));

// When the value is undefined, defaultValue
// is returned by _.defaultTo() method
console.log(_.defaultTo(undefined, 43));
```

**输出:**

```
15
43
```