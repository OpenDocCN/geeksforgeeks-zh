# Lodash _.startsWith() 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-startswith-method/](https://www.geeksforgeeks.org/lodash-_-startswith-method/)

`_.startsWith()` 方法用于查找字符串是否以给定的目标字符串开始。如果字符串以给定的目标字符串开头，则返回 `true`。否则，它返回 `false`。

**语法:**

```
_.startsWith( [string = ''], [target], [position = 0] )
```

**参数:** 该方法接受三个参数，如下所述:

*   `string`: 此参数存储要检查的字符串。
*   `target`: 此参数存储要搜索的字符串。
*   `position`: 此参数存储开始搜索的位置。

**返回值:** 如果字符串以目标字符串开头，则该方法返回 `true`，否则返回 `false`。

以下示例说明了 Lodash 中的 `_.startsWith()` 方法:

**例 1:**

```javascript
// Requiring the lodash library
const _ = require("lodash");

// Use of _.startsWith() method
console.log(_.startsWith('geeksforgeeks', 'g'));
console.log(_.startsWith('geeksforgeeks', 'f'));
```

**输出:**

```
true
false
```

**例 2:**

```javascript
// Requiring the lodash library
const _ = require("lodash");

// Use of _.startsWith() method
console.log(_.startsWith('geeksforgeeks', 'e', 1 ));
console.log(_.startsWith('geeksforgeeks', 'e', 4 ));
console.log(_.startsWith('geeksforgeeks', 'e', 10));
```

**输出:**

```
true
false
true
```