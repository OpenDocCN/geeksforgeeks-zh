# Lodash _.endsWith() 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-endswith-method/](https://www.geeksforgeeks.org/lodash-_-endswith-method/)

Lodash 是一个工作在 Underscore.js 之上的 JavaScript 库，有助于处理数组、字符串、对象、数字等。

`_.endsWith()` 方法用于检查字符串是否以给定的目标字符串结尾。

**语法:**

```javascript
_.endsWith([string=''], [target], [position=string.length])
```

**参数:** 该方法接受三个参数，如下所述：

*   `string`: 该参数保存需要检查的字符串。
*   `target`: 此参数保存需要搜索的字符串。
*   `position`: 此参数保存搜索字符串的位置。

**返回值:** 如果字符串以目标字符串结尾，则此方法返回 `true`，否则返回 `false`。

**例 1:**

### JavaScript

```javascript
const _ = require('lodash');

var str1 = _.endsWith("GeeksforGeeks", "s");
console.log(str1);

var str2 = _.endsWith("GeeksforGeeks", "G");
console.log(str2);

var str3 = _.endsWith("GeeksforGeeks", "Geeks");
console.log(str3);
```

**输出:**

```
true
false
true
```

**例 2:**

### JavaScript

```javascript
const _ = require('lodash');

var str1 = _.endsWith("GFG", "F", 2);
console.log(str1);

var str2 = _.endsWith("GeeksforGeeks", "f", 5);
console.log(str2);

var str3 = _.endsWith("GeeksforGeeks", "for", 8);
console.log(str3);
```

**输出:**

```
true
false
true
```