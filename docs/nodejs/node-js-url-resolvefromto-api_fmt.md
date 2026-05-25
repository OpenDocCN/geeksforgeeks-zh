# Node.js URL.resolve(from, to) API

> 原文: [https://www.geeksforgeeks.org/node-js-url-resolvefromto-api/](https://www.geeksforgeeks.org/node-js-url-resolvefromto-api/)

`URL.resolve(from, to)` 是类 `URL` 的内置方法，它相对于**基本 URL** 解析**目标 URL**。

## 语法:

```js
url.resolve(from, to);
```

*   `from`: (类型: 字符串) 解析的基本网址。
*   `to`: (类型: 字符串) 正在解析的“href”网址。

## 返回值:

它通过在 `from` 中给定的参数返回解析后的 `to` 网址 (类型: 字符串)。

## 解析目标网址:

1.  以正斜杠 (`/`) 开头 – 它将替换基本网址域后的整个路径。
2.  前面没有正斜杠 (`/`) – 它将替换基本网址路径中正斜杠 (`/`) 后的最后一个单词。

## 示例:

```js
// node program to demonstrate the
// url.resolve(from, to) method

// importing the module 'url'
const url = require('url');

// We can directly console.log() return value of the method

// Method 1:
console.log(url.resolve("http://www.google.com/", "/one"));
console.log(url.resolve("http://www.google.com/one/two/three", "/four"));

// Method 2:
console.log(url.resolve("http://www.google.com/", "one"));
console.log(url.resolve("http://www.google.com/one/two/three", "four"));
```

```js
OUTPUT:
http://www.google.com/one
http://www.google.com/four

http://www.google.com/one
http://www.google.com/one/two/four
```

## 注意:

这段代码可以在命令提示符下用 `node` 命令运行。(例如 `node filename`)