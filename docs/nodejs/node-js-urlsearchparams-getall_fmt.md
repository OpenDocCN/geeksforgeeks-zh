# Node.js URLSearchParams.getAll()

> 来源: https://www.geeksforgeeks.org/node-js-urlsearchparams-getall/

在`URLSearchParams`接口中，`getAll()`方法以数组的形式返回输入搜索参数的所有值。

## 语法

```js
URLSearchParams.getAll(name)
```

## 返回值

根据名称返回对应的字符串数组，否则返回空数组。

## 参数

- `name` – 输入参数名称。

## 示例 1

```js
let url = new URL('https://example.com?par=5&bar=2'); 
let params = new URLSearchParams(url.search.slice(1));

// Add a second par parameter. 
params.append('par', 4);

console.log(params.getAll('par'));
```

**输出:**

```js
['5', '4']
```

## 示例 2: 当输入参数不存在时

```js
let url = new URL('https://example.com?par=5&bar=2&bar=7&par=4&bar=9'); 
let params = new URLSearchParams(url.search.slice(1));

console.log(params.getAll('bar'));
```

**输出:**

```js
['2','7','9']
```

## 支持的浏览器

- Google Chrome
- Internet Explorer
- Edge
- Opera
- Safari