# 下划线.js _.selectKeys()方法

> 原文：[https://www.geeksforgeeks.org/underscore-js-_-selectkeys-method/](https://www.geeksforgeeks.org/underscore-js-_-selectkeys-method/)

`_.selectKeys()` 方法返回一个仅包含给定数组中列出的属性的对象的副本。

**语法：**

```javascript
_.selectKeys( Object_name, array );
```

**参数：**

*   `Object_name`：从中选择键/值对的对象。
*   `array`：给定包含要列出的属性的数组。

**返回值：** 此方法返回包含所列属性的对象的副本。

**注意：** 这在正常的 JavaScript 中无法工作，因为它需要安装下划线.js contrib 库。

可以使用 `npm install underscore-contrib` 来安装下划线.js contrib 库。

**例 1：**

## JavaScript

```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var obj = {
    1: "Gfg1",
    2: "Gfg2",
    3: "Gfg3"
};

var val = _.selectKeys(obj, [1, 3]);
console.log(val);
```

**输出：**

```javascript
{ '1': 'Gfg1', '3': 'Gfg3' }
```

**例 2：** 如果在对象中没有找到属性，这个方法返回一个空对象。

## JavaScript

```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var obj = {
    1: "Gfg1",
    2: "Gfg2",
    3: "Gfg3"
};

var val = _.selectKeys(obj, [4]);
console.log(val);
```

**输出：**

```javascript
{}
```