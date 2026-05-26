# 下划线.js _.renameKeys()方法

> 原文: [https://www.geeksforgeeks.org/underscore-js-_-renamekeys-method/](https://www.geeksforgeeks.org/underscore-js-_-renamekeys-method/)

`_.renameKeys()`方法获取一个对象和一个映射对象，并返回一个新的对象，其中给定的对象的键已被重命名为键映射中的相应值。

**语法:**

```
_.renameKeys(obj, mapObj);
```

**参数:**

*   `obj`: 给定对象创建新对象。
*   `mapObj`: 给定贴图对象创建新对象。

**返回值:** 这个方法返回一个生成的对象。

**注意:** 这在正常的 JavaScript 中无法工作，因为它需要安装下划线.js contrib 库。

可以使用 `npm install underscore-contrib` 来安装下划线.js contrib 库。

**例 1:**

## JavaScript

```
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var obj = _.renameKeys( { 1 : "Geeks",
            2 : "Computer_Science_Portal" },
            { 1 : "g", 2 : "c" });

console.log("Generated Object: ", obj);
```

**输出:**

```
Generated Object:  { g: 'Geeks', c: 'Computer_Science_Portal' }
```

**示例 2:** 如果对象中的两个或多个键值对变得相同，则生成的对象将具有唯一的键值对。

## JavaScript

```
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var obj = _.renameKeys(
    { 1 : "Geeks", 2 : "Computer_Science_Portal",
    3 : "Geeks" }, { 1 : "g", 2 : "c", 3 : "g" });

console.log("Generated Object: ", obj);
```

**输出:**

```
Generated Object:  { g: 'Geeks', c: 'Computer_Science_Portal' }
```

**示例 3:** 如果给定的对象是数组，将使用该数组的对象索引映射创建的新对象。

## JavaScript

```
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var obj = _.renameKeys( [ "Computer_Science_Portal", "Geeks" ],
                        { 0 : "a", 1 : "b", 3 : "g" });

console.log("Generated Object: ", obj);
```

**输出:**

```
Generated Object:  { a: 'Computer_Science_Portal', b: 'Geeks' }
```