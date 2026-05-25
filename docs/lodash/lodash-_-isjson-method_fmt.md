# Lodash `_.isJSON()` 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-isjson-method/](https://www.geeksforgeeks.org/lodash-_-isjson-method/)

`_.isJSON()` 方法检查给定值是否为有效的 JSON，并返回相应的布尔值。

**语法:**

```javascript
_.isJSON( value );
```

**参数:** 该方法取上述单参数，描述如下:

*   `value`: 要检查 JSON 的给定值。

**返回值:** 如果给定值为有效 JSON，则该方法返回布尔值 `true`，否则返回 `false`。

**注意:** 这在正常的 JavaScript 中不会起作用，因为它需要安装 `lodash-contrib` 库。可以使用 `npm install lodash-contrib` 来安装。

**例 1:**

### JavaScript

```javascript
// Defining lodash contrib variable 
var _ = require('lodash-contrib');

// Checking for _.isJSON() method
console.log("The Value is JSON : " +_.isJSON( 
'{"GeeksforGeeks" : "A Computer Science portal for Geeks"}'));
```

**输出:**

```
The Value is JSON : true
```

**例 2:**

### JavaScript

```javascript
// Defining lodash contrib variable 
var _ = require('lodash-contrib');

// Checking for _.isJSON() method
console.log("The Value is JSON : " +_.isJSON( 
{GeeksforGeeks : "A Computer Science portal for Geeks"}));
```

**输出:**

```
The Value is JSON : false
```

**例 3:**

### JavaScript

```javascript
// Defining lodash contrib variable 
var _ = require('lodash-contrib');

// Checking for _.isJSON() method
console.log("The Value is JSON : " + _.isJSON(["gfg"]));
```

**输出:**

```
The Value is JSON : false
```