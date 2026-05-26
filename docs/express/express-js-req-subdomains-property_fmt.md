# Express.js req.subdomains 属性

> 原文: [https://www.geeksforgeeks.org/express-js-req-subdomains-property/](https://www.geeksforgeeks.org/express-js-req-subdomains-property/)

`req.subdomains` 属性在请求的域名中包含一个子域数组。应用程序属性 `subdomainOffset`，默认为 2，决定子域段的开始。

**语法:**

```js
req.subdomains
```

**参数:** 无参数。
**返回:** 数组

**Express 模块安装:**

1.  您可以访问[安装 Express 模块](https://www.npmjs.com/package/express)的链接。您可以使用此命令安装此软件包。

```js
npm install express
```

2.  安装 Express 模块后，您可以使用命令在命令提示符下检查您的 Express 版本。

```js
npm version express
```

3.  之后，您可以创建一个文件夹并添加一个文件，例如 `index.js`。

```js
node index.js
```

## 示例 1

### 文件名: index.js

```js
var express = require('express');
var app = express();
var PORT = 3000;

app.get('/', function (req, res) {
  console.log(req.subdomains);
  res.send();
});

app.listen(PORT, function(err){
    if (err) console.log(err);
    console.log("Server listening on PORT", PORT);
});
```