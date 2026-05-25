# Lodash _.gt() 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-gt-method/](https://www.geeksforgeeks.org/lodash-_-gt-method/)

`_.gt()` 方法是用来判断一个数值是否大于另一个数值。如果该值大于另一个值，则返回 `true`。否则，它返回 `false`。

## 语法

```
_.gt(value, other)
```

## 参数

该方法接受两个参数：

*   `value`: 此参数持有要比较的值。
*   `other`: 此参数存储用于比较的另一个值。

## 返回值

如果 `value` 大于 `other`，则该方法返回 `true`，否则返回 `false`。

## 例 1

```javascript
// Requiring the lodash library
const _ = require("lodash");

// Use of _.gt method
console.log(_.gt(19, 8));
console.log(_.gt(15, 17));
```

**输出:**

```
true
false
```

## 例 2

```javascript
// Requiring the lodash library
const _ = require("lodash");

// Use of _.gt method
console.log(_.gt(13, 13));
console.log(_.gt(29, 17));
```

**输出:**

```
false
true
```