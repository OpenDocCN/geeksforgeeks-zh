# Node.js URLObject.query API

> 原文：[https://www.geeksforgeeks.org/node-js-urlobject-query-api/](https://www.geeksforgeeks.org/node-js-urlobject-query-api/)

`urlObject.query` 是返回的查询字符串，不带 ASCII 问号（`?`），或是由 `parse()` 方法（来自 `querystring` 模块）返回的对象。`Url.parse()` 方法用于检查查询是字符串还是对象。基本上，传递给 `url.parse()` 方法的参数（`parseQueryString`）决定了查询的性质。

## 语法

```js
urlObject.query
```

**注意：** 如果这个方法返回一个字符串，那么不执行对查询字符串的解码；如果它返回一个对象，那么键值对都会被解码。

## 示例

```js
'query=string' or {'query': 'object'}

'http://localhost:8000/gfg.html?name:GFG'
```
在上面的 URL 中，`name` 是查询键，`GFG` 是字符串值。

下面的程序说明了在 Node.js 中 `url.query` 方法的使用：

### 示例 1

```js
// Node program to demonstrate the   
// url.query API as Setter

// Importing the module 'url'
var url = require('url');

// Set the URL from which the queryString will be fetched
var address = 'http://localhost:8000/gfg.html?month=Decemeber';

// Parse the address
var q = url.parse(address, true);

// The query property returns an object with all the
// querystring parameters as properties
var query = q.query;

var month = query.month;

console.log(month);
```

**输出：**

```js
December
```

### 示例 2

```js
// Node program to demonstrate the   
// url.query API as Setter

// Importing the module 'url'
var url = require('url');

// Set the URL from which the queryString will be fetched
var address = 'http://localhost:8000/gfg.html?month=Decemeber&year=2019';

// Parse the address
var q = url.parse(address, true);

// The query property returns an object with all the
// querystring parameters as properties
var query = q.query;

var year = query.year;

console.log(year);
```

**输出：**

```js

```

**参考：** [https://nodejs.org/api/url.html#url_urlobject_query](https://nodejs.org/api/url.html#url_urlobject_query)