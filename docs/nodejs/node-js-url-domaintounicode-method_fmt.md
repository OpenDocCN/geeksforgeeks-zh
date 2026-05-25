# node.js URL.domainToUnicode()方法

> 原文: [https://www.geeksforgeeks.org/node-js-url-domaintounicode-method/](https://www.geeksforgeeks.org/node-js-url-domaintounicode-method/)

`URL.domainToUnicode()`方法是一个内置的应用程序编程接口类`URL`与`url`模块，用于获取特定 ASCII 值的域。

## 语法:

```js
const url.domainToUnicode(domain)
```

## 参数:

该方法以 ASCII 值为参数，即将转换为 Unicode。

## 返回值:

该方法返回特定域的 unicode 值。

下面的程序说明了`URL.domainToUnicode()`方法的使用。

### 例 1:

```js
// Node.js program to demonstrate the 
// URL.domainToUnicode() method

// Importing the 'url' module
const http = require('url');

// Getting Unicode value
// by using domainToUnicode() api
const ascivalue = http.domainToUnicode(
            "xn--espaol-zwa.com");

// Display result for each value entry
console.log("Unicode value : " + ascivalue);

// Getting Unicode value
// by using domainToUnicode() api
const ascivalue1 = http.domainToUnicode("google.com");

// display result for each value entry
console.log("\nUnicode value : " + ascivalue1);
```

**输出:**

```js
Unicode value : español.com

Unicode value : google.com
```

### 例 2:

```js
// Node.js program to demonstrate the 
// URL.domainToUnicode() API as Setter

// Importing the module 'url'
const http = require('url');

// Getting Unicode value
// by using domainToUnicode() api
const ascivalue = http.domainToUnicode(
            "geeksforgeeks.com");

// Display result for each value entry
console.log("Unicode value : " + ascivalue);

// Getting Unicode value
// by using domainToUnicode() api
const ascivalue1 = http.domainToUnicode("xn--iñvalid.com");

// Display result for each value entry
console.log("\nUnicode value : " + ascivalue1);
```

**输出:**

```js
Unicode value : geeksforgeeks.com

Unicode value :
```

**注意**: 以上程序不会在在线 JavaScript 和脚本编辑器上运行。

**参考:** [https://nodejs.org/dist/latest-v14.x/docs/api/url.html#url_url_domaintounicode_domain](https://nodejs.org/dist/latest-v14.x/docs/api/url.html#url_url_domaintounicode_domain)