# Lodash _.omit() 方法

> 原文: [`https://www.geeksforgeeks.org/lodash-_-omit-method/`](https://www.geeksforgeeks.org/lodash-_-omit-method/)

Lodash 是一个工作在 Underscore.js 之上的 JavaScript 库，有助于处理数组、字符串、对象、数字等。

`_.omit()` 方法用于返回对象的副本，该副本由给定对象的自身和继承的可枚举属性路径组成，这些路径没有被省略。它与 `_.pick()` 方法相反。

## 语法

```javascript
_.omit( object, paths )
```

## 参数

该方法接受两个参数：

*   `object`: 此参数保存源对象。
*   `paths`: 此参数保存要省略的属性路径的数组。

## 返回值

该方法返回新对象。

## 示例 1

### JavaScript

```javascript
// Requiring the lodash library
const _ = require("lodash");

// The source object
var obj = {
            Name: "GeeksforGeeks",
            password: "gfg@1234",
            username: "your_geeks"
        }

// Using the _.omit() method
console.log(_.omit(obj, ['password', 'username']));
```

**输出:**

```javascript
{Name: "GeeksforGeeks"}
```

## 示例 2

### JavaScript

```javascript
// Requiring the lodash library
const _ = require("lodash");

// The source object
var obj = { 'x': 1, 'y': '2', 'z': 3 };

// Use the _.omit() method
console.log(_.omit(obj, ['x', 'y']));
```

**输出:**

```javascript
{'z': 3}
```