# Node.js 查询字符串

> 原文：[https://www.geeksforgeeks.org/node-js-query-string/](https://www.geeksforgeeks.org/node-js-query-string/)

`querystring`模块用于提供解析和格式化网址查询字符串的实用程序。它可以用来将查询字符串转换成 JSON 对象，反之亦然。

查询字符串是在问号(？)之后的部分。

## 要求模块

您可以使用以下代码包含该模块：

```js
const querystring = require('querystring');
```

**注意：**`querystring`不是全局对象，需要明确安装。

## 安装模块

```bash
npm install querystring
```

## 示例

### 示例 1：使用 `parse()`

```js
// Importing the models
import url from 'url'
import querystring from 'querystring'

// A URL is taken
let exampleUrl = 'http://www.company.com:81/a/b/c.html?user=GEEKSFORGEEKS&year=2021#p2';

//Parse the whole URL
let parsed_Url = url.parse(exampleUrl);

// Parse only querystring.
let parsed_queryString = querystring.parse(parsed_Url.query);

// Print thr result.
console.log("This is parsed URL :",parsed_Url);

console.log("This is parsed Query String :",parsed_queryString);
```

**输出：**

```js
This is parsed URL : Url {
  protocol: 'http:',
  slashes: true,
  auth: null,
  host: 'www.company.com:81',
  port: '81',
  hostname: 'www.company.com',
  hash: '#p2',
  search: '?user=GEEKSFORGEEKS&year=2021',
  query: 'user=GEEKSFORGEEKS&year=2021',
  pathname: '/a/b/c.html',
  path: '/a/b/c.html?user=GEEKSFORGEEKS&year=2021',
  href: 'http://www.company.com:81/a/b/c.html?user=GEEKSFORGEEKS&year=2021#p2'
}
This is parsed Query String : [Object: null prototype] { user: 'GEEKSFORGEEKS', year: '2021' }
```

### 示例 2：使用 `stringify()`

```js
// Importing the model
import querystring from 'querystring'

// Specify the object to be serialized
const q2=querystring.stringify({
    name:'Testing',
    company:'GeeksforGeeks',
    content:'Article',
    date:'9thMarch2021'
});

// Print the result.
console.log(q2);
```

**输出：**

```js
name=Testing&company=GeeksforGeeks&content=Article&date=9thMarch2021
```

**参考：**[https://nodejs.org/api/querystring.html](https://nodejs.org/api/querystring.html)