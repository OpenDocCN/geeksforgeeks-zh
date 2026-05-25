# Node.js `indexOf()`函数

> 原文：[https://www.geeksforgeeks.org/node-js-indexof-function/](https://www.geeksforgeeks.org/node-js-indexof-function/)

`indexOf()`函数是一个来自 [Node.js](https://www.geeksforgeeks.org/introduction-to-nodejs/) 的字符串函数，用于在一个字符串中查找另一个字符串。

## 语法

```js
*str1*.indexOf( *str2* )
```

## 参数

该函数使用两个参数，如下所述：

*   `str1`：它持有要被搜索的另一个字符串的内容。
*   `str2`：它持有搜索字符串。

## 返回值

函数返回传递参数的索引。

以下程序演示了 `indexOf()`函数的工作原理：

### 节目 1

```js
function findIndex(str) {
    var index = str.indexOf("awesome");
    console.log(index);
}

var str = "gfg is awesome";

findIndex(str);
```

### 输出

```js

```

### 节目 2

```js
function findIndex(str1, str2) {
    var index = str1.indexOf(str2);
    console.log(index);
}

var str1 = "Welcome to GeeksforGeeks";
var str2 = "to"

findIndex(str1, str2);
```

### 输出

```js

```