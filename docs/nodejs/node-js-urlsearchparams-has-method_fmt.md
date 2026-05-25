# Node.js URLSearchParams.has()方法

> 原文: [https://www.geeksforgeeks.org/node-js-urlsearchparams-has-method/](https://www.geeksforgeeks.org/node-js-urlsearchparams-has-method/)

在`URLSearchParams`接口中，`has()`方法返回一个布尔值，告诉我们输入名称的参数是否存在，存在则返回 `true`，否则返回 `false`。

## 语法

```js
var Bool = URLSearchParams.has(name)
```

## 返回值
真 – 如果名称存在，否则将返回假。

## 参数
`name` – 输入参数名称。

## 示例 1

```js
let url = new URL('https://example.com?par=5&bar=4');
let param = new URLSearchParams(url.search.slice(1));

param.has('bar') === true;
```

**输出:**

```js
true
```

## 示例 2: 当输入参数不存在时

```js
let url = new URL('https://example.com?par=5&bar=4');
let param = new URLSearchParams(url.search.slice(1));

param.has('foo') === true;
```

**输出:**

```js
false
```

## 支持的浏览器

*   谷歌 Chrome
*   工业管理学(Industrial Engineering)
*   边缘
*   歌剧
*   苹果 Safari