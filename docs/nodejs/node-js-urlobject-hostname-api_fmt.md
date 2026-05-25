# Node.js URL Object Hostname API

> 原文：[https://www.geeksforgeeks.org/node-js-urlobject-hostname-api/](https://www.geeksforgeeks.org/node-js-urlobject-hostname-api/)

`url.hostname` 是 `url` 模块中 `URL` 类的内置应用程序编程接口，用于获取和设置 URL 的主机名部分。`url.hostname` 不包括端口号。

## 语法

```js
url.hostname
```

它通过单个值与 `URL` 关联，`URL` 是由 `URL` 构造器创建的对象。

## 示例

```js
// Node program to demonstrate the
// url.hostname API as both Getter and Setter

// Imports only single export 'URL'
// from url module using ES6 syntax
const { URL } = require('url');

// Creating and initializing myURL
// object using URL constructor
const myURL = new URL('https://gfg.org:80/foo#ram');

// Display hostname value of myURL before change
console.log("Before Change");
console.log(myURL.hostname);

console.log('');

// Updating hostname portion
// using hostname method
myURL.hostname = 'example2.com';

// Display hostname value of myURL after updating
console.log("After Change");
console.log(myURL.hostname);
```

## 输出

```js
Before Change
gfg.org

After Change
geeksforgeeks.org
```

## 参考

[https://nodejs.org/dist/latest-v10.x/docs/api/url.html#url_url_hostname](https://nodejs.org/dist/latest-v10.x/docs/api/url.html#url_url_hostname)