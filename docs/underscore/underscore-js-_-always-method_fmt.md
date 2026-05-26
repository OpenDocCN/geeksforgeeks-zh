# Underscore.js _.always() 方法

> 原文: [https://www.geeksforgeeks.org/underscore-js-_-always-method/](https://www.geeksforgeeks.org/underscore-js-_-always-method/)

`_.always()` 方法接受一个值并返回一个函数，该函数将始终返回那个值。

**语法:**

```
_.always( value );
```

**参数:**

*   `value`: 此方法接受一个要返回的值。

**返回值:** 此方法返回一个函数。

**注意:** 这在正常的 JavaScript 中无法工作，因为它需要安装 Underscore.js contrib 库。可以使用 `npm install underscore-contrib` 来安装 Underscore.js contrib 库。

**例 1:**

## Javascript

```
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var gfgFunc = _.always('Geeks');
console.log(gfgFunc());
```

**输出:**

```
Geeks
```

**例 2:**

## Javascript

```
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var gfgFunc = _.always(1);
console.log("Value returned is", gfgFunc());
```

**输出:**

```
Value returned is 1
```