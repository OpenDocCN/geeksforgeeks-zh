# `_.unescape()`方法

> 原文：[https://www.geeksforgeeks.org/lodash-_-unescape-method/](https://www.geeksforgeeks.org/lodash-_-unescape-method/)

Lodash 是一个工作在下划线之上的 JavaScript 库。Lodash 有助于处理数组、字符串、对象、数字等。

`_.unescape()`方法用于转换类似`&amp;`、`&lt;`、`&gt;`、`&quot;`和`&#39;`在给定的字符串中对应到它们的字符。

**语法：**

```javascript
_.unescape( string )
```

**参数：** 该方法接受如上所述的单个参数，描述如下：

*   `string`：是用于非转义的字符串。

**返回值：** 此方法返回未转义的字符串。

## 例 1

```javascript
// Defining Lodash variable 
const _ = require('lodash');

// The string to unescape
var str = "fit & fine";

// Using _.unescape() method
console.log(_.unescape(str));
```

**输出：**

```
fit & fine
```

## 例二

```javascript
// Defining Lodash variable 
const _ = require('lodash');

// The string to unescape
var str = "&quot;Heyy&quot;";

// Using _.unescape() method
console.log(_.unescape(str));
```

**输出：**

```
"Heyy"
```