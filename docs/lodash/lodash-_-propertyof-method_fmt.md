# Lodash _.propertyOf() 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-propertyof-method/](https://www.geeksforgeeks.org/lodash-_-propertyof-method/)

Lodash `_.propertyOf()` 方法是 `_.property()` 函数的逆操作。此函数将对象作为参数，并返回一个函数，该函数将返回所提供属性的值。

## 语法

```
_.propertyOf( object )
```

## 参数

该方法接受一个参数，如下所述：

*   `object`: 该参数保存该方法需要返回的对象的值。

## 返回值

此方法返回一个新的访问器函数。

## 示例 1

```javascript
// Requiring the lodash library
const _ = require("lodash");

var info = {
            Company: 'GeeksforGeeks',
            Address: 'Noida'
        };

// Use of _.propertyOf() method
let gfg = _.propertyOf(info)('Company')

// Printing the output
console.log(gfg);
```

**输出:**

```
GeeksforGeeks
```

## 示例 2

```javascript
// Requiring the lodash library
const _ = require("lodash");

var array = [0, 2],
    object = { 'a': array, 'b': array };

// Use of _.propertyOf() method
let gfg = _.map(['a[0]', 'b[1]'], _.propertyOf(object));

// Printing the output
console.log(gfg);
```

**输出:**

```
[0, 2]
```