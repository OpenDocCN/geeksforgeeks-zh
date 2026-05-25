# Lodash _.implode()方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-implode-method/](https://www.geeksforgeeks.org/lodash-_-implode-method/)

`_.implode()`方法用于将字符串数组内爆为单个字符串。

## 语法

```
_.implode( array );
```

## 参数

该方法取上述单参数，描述如下:

*   `array`: 这个方法需要一个数组才能内爆。

## 返回值

这个方法返回生成的字符串。

## 注意

这在正常的 JavaScript 中不会起作用，因为它需要安装 `lodash.js contrib` 库。可以使用 `npm install lodash.js contrib库--save`。

## 例 1

### JavaScript

```
// Defining lodash contrib variable
var _ = require('lodash-contrib');

var s = _.implode( [
    "G", "e", "e", "k", "s",
    "f", "o", "r",
    "G", "e", "e", "k", "s"
] );

console.log("The generated String is : ", s);
```

**输出:**

```
The generated String is : GeeksforGeeks
```

## 例 2

### JavaScript

```
// Defining lodash contrib variable
var _ = require('lodash-contrib');

var s = _.implode( [
    "C", "o", "m", "p", "u", "t",
    "e", "r", " ", "S", "c", "i",
    "e", "n", "c", "e", " ", "P",
    "o", "r", "t", "a", "l"
] );

console.log("The generated String is : ", s);
```

**输出:**

```
The generated String is : Computer Science Portal
```