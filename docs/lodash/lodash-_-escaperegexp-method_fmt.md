# Lodash _.escapeRegExp() 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-escaperegexp-method/](https://www.geeksforgeeks.org/lodash-_-escaperegexp-method/)

`_.escapeRegExp` 方法用于转义字符串中的正则表达式特殊字符，包括 `"^"`, `"$"`, `"."`, `"*"`, `"+"`, `"?"`, `"("`, `")"`, `"["`, `"]"`, `"{"`, `"}"` 和 `"|"`。

## 语法

```
_.escapeRegExp([string=''])
```

## 参数

该方法接受如上所述的单个参数，如下所述：

* `string`: 此参数持有需要被转义的字符串。

## 返回值

此方法返回转义后的字符串。

## 示例 1

### JavaScript

```
const _ = require('lodash');

var str1 = _.escapeRegExp("/a/");
console.log(str1);

var str2 = _.escapeRegExp("\*?{}.");
console.log(str2);
```

### 输出

```
"/a/"
"\\*\\?\\{\\}\\."
```

## 示例 2

### JavaScript

```
const _ = require('lodash');

var str1 = _.escapeRegExp("/geeks/");
console.log(str1);

var str2 = _.escapeRegExp("/(?<geeks>.)(?<for>.)(?<geeks>.)/");
console.log(str2);

var str3 = _.escapeRegExp("\*?????{}.");
console.log(str3);
```

### 输出

```
"/geeks/"
"/\\(\\?<geeks>\\.\\)\\(\\?<for>\\.\\)\\(\\?<geeks>\\.\\)/"
"\\*\\?\\?\\?\\?\\?\\{\\}\\."
```