# Underscore.js `_.kv()` 方法

> 原文: [https://www.geeksforgeeks.org/underscore-js-_-kv-method/](https://www.geeksforgeeks.org/underscore-js-_-kv-method/)

`_.kv()` 方法返回对象中给定属性的键/值对，如果找不到则返回 `undefined`。

**语法:**

```javascript
_.kv( Object_name, property );
```

**参数:**

*   `Object_name`: 要搜索键/值对的对象。
*   `Attribute`: 指定要搜索哪个键/值对的属性。

**返回值:** 这个方法为给定的属性设置键/值对。

**注意:** 这在正常的 JavaScript 中无法工作，因为它需要安装 Underscore.js contrib 库。

可以使用 `npm install underscore-contrib` 来安装 Underscore.js contrib 库。

## 示例 1

```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var ob = { "gfg" : "GeeksforGeeks" };
var val = _.kv( ob, "gfg");

console.log(val);
```

**输出:**

```
[ 'gfg', 'GeeksforGeeks' ]
```

## 示例 2

如果没有找到键/值，这个方法返回 `undefined`。

```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var ob = { "gfg" : "GeeksforGeeks" };
var val = _.kv( ob, "geek");

console.log(val);
```

**输出:**

```
undefined
```