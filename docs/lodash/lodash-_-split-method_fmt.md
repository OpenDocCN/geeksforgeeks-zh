# Lodash _.split() 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-split-method/](https://www.geeksforgeeks.org/lodash-_-split-method/)

`_.split()` 方法按照给定的分隔符对给定的字符串进行拆分，最多可达给定的限制长度。

## 语法

```javascript
_.split( string, separator, limit )
```

## 参数

此方法接受三个参数，如下所述：

*   `string`: 要拆分的字符串。
*   `separator`: 用于拆分字符串的分隔符。
*   `limit`: 结果要截取的长度。

## 返回值

这个方法返回一个数组。

## 示例 1

```javascript
// Defining Lodash variable 
const _ = require('lodash');

var str = "Geeks-for-Geeks";

// Using _.split() method
console.log(_.split(str, '-' ))
```

**输出:**

```
[ 'Geeks', 'for', 'Geeks' ]
```

## 示例 2

数组大小限制为 1。

```javascript
// Defining Lodash variable 
const _ = require('lodash');

var str = "Geeks-for-Geeks";

// Using _.split() method
console.log(_.split(str, '-', 1 ))
```

**输出:**

```
[ 'Geeks' ]
```

**注意:** 这在正常的 JavaScript 中不会起作用，因为它需要安装 lodash 库，可以使用 `npm install lodash` 进行安装。