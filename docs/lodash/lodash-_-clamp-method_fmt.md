# Lodash _.clamp()方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-clamp-method/](https://www.geeksforgeeks.org/lodash-_-clamp-method/)

`_.clamp()`方法用于将数字钳制在上下界范围内。

## 语法

```javascript
_.clamp(number, lower, upper)
```

## 参数

该方法接受三个参数，如下所述：

*   `number`: 此参数存储要被钳制的数字。
*   `lower`: 此参数作为下限。
*   `upper`: 此参数作为上限。

## 返回值

此方法返回钳制后的数字。

## 示例 1

### JavaScript

```javascript
// Requiring the lodash library
const _ = require("lodash");

// Use of _.clamp method
console.log(_.clamp(2, 3, 5));
console.log(_.clamp(2, -2, -5));
```

**输出:**

```javascript

```

## 示例 2

### JavaScript

```javascript
// Requiring the lodash library
const _ = require("lodash");

// Use of _.clamp method
console.log(_.clamp(15, -13, 13));
console.log(_.clamp(-15, -13, 13));
```

**输出:**

```javascript

```