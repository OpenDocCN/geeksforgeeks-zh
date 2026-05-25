# Node.js URLSearchParams.toString() 方法

> 原文：[https://www.geeksforgeeks.org/node-js-urlsearchparams-tostring-method/](https://www.geeksforgeeks.org/node-js-urlsearchparams-tostring-method/)

`URLSearchParams.toString()` 方法是 `url` 模块中 `URLSearchParams` 类的内置应用编程接口，用于将 URL 搜索参数对象作为字符串获取。

**语法：**

```js
const urlSearchParams.toString()
```

**参数：** 此方法不接受任何参数。
**返回值：** 该方法以字符串形式返回 URL 搜索参数对象。

下面的程序说明了 `URLSearchParams.toString()` 方法在 Node.js 中的使用。

**示例 1：**

文件名：`app.js`

```js
// Node.js program to demonstrate the
// URLSearchParams.toString() method

// Importing the module 'url'
const http = require('url');

// Creating and initializing
// URLSearchParams object
const params = new URLSearchParams();

// Appending value in the object
params.append('A', 'Book');
params.append('B', 'Pen');
params.append('A', 'Pencil');

// Getting string representation
// by using toString() api
const value = params.toString();

// Display the result
console.log("String representation"
      + " of object : " + value);
```

使用以下命令运行 `app.js` 文件：

```js
node app.js
```

**输出：**

```js
String representation of object : A=Book&B=Pen&A=Pencil
```

**示例 2：**

文件名：`app.js`

```js
// Node.js program to demonstrate the
// URLSearchParams.toString() method

// Importing the module 'url'
const http = require('url');

// Creating and initializing
// URLSearchParams object
const params = new URLSearchParams();

// Appending value in the object
params.append('geeks', 'code');
params.append('for', 'eat');
params.append('geeks', 'sleep');

// Getting string reprsentation
// by using toString() api
const value = params.toString();

// Display the result
console.log("String representation"
      + " of object : " + value);
```

使用以下命令运行 `app.js` 文件：

```js
node app.js
```

**输出：**

```js
String representation of object : geeks=code&for=eat&geeks=sleep
```

**参考：** [https://nodejs.org/dist/latest-v14.x/docs/api/url.html#url_urlsearchparams_tostring](https://nodejs.org/dist/latest-v14.x/docs/api/url.html#url_urlsearchparams_tostring)