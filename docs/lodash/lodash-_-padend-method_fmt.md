# 洛达什 `_.padEnd()` 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-padend-method/](https://www.geeksforgeeks.org/lodash-_-padend-method/)

`_.padEnd()` 方法是用一个字符串填充另一个字符串，直到达到给定的长度。填充从字符串的右端开始应用。如果填充字符超过长度，将被截断。

**语法:**

```javascript
_.padEnd( [string = ''], [length = 0], [chars = ' '] )
```

**参数:** 该方法接受三个参数，如上所述，如下所述:

*   `string`: 此参数保存要填充的字符串。
*   `length`: 此参数存储填充后的长度。
*   `chars`: 此参数保存用作填充的字符串。

**返回值:** 这个方法返回填充后的字符串。

下面的例子说明了 Lodash 中的 `_.padEnd()` 方法:

**例 1:**

### Javascript

```javascript
// Requiring the lodash library
const _ = require("lodash");

// Use of _.padEnd() method
console.log(_.padEnd('GFG', 5));
console.log(_.padEnd('1234', 6, '#'));
```

**输出:**

```
'GFG  '
'1234##'
```

**例 2:**

### Javascript

```javascript
// Requiring the lodash library
const _ = require("lodash");

// Use of _.padEnd() method
console.log(_.padEnd('GFG', 6, '-'));
console.log(_.padEnd('1234', 3, '#'));
```

**输出:**

```
'GFG---'
'1234'
```