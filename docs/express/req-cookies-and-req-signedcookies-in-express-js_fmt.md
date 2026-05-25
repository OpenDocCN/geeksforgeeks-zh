# req.cookies 和 req.signedCookies in Express.js

> 原文: [https://www.geeksforgeeks.org/req-cookies-and-req-signedcookies-in-express-js/](https://www.geeksforgeeks.org/req-cookies-and-req-signedcookies-in-express-js/)

## req.cookies

`req.cookies` 属性包含来自客户端（浏览器）请求的 cookie。Cookies 是通过服务器请求发送到客户端并存储在客户端的小文件/数据，有助于跟踪用户行为。

Cookie 解析器是一个中间件，用于解析附加到客户端请求对象的 cookie。当我们使用 `cookieParser()` 中间件时，`req.cookies` 属性是一个包含请求发送的 cookie 的对象。如果请求不包含 cookies，则默认为 `{}`。

### 示例

```js
var cookieParser = require('cookie-parser');
var express = require('express');
var app = express();
var PORT = 3000;

app.use(cookieParser());

app.get('/user', function (req, res) {
    req.cookies.name = 'Gourav';
    req.cookies.age = 12;

    console.log(req.cookies);
    res.send();
});

app.listen(PORT, function(err){
    if (err) console.log(err);
    console.log("Server listening on PORT", PORT);
});
```

### 输出

现在打开浏览器，向 `http://localhost:3000/user` 发出 GET 请求，现在可以在控制台上看到如下输出：

```js
Server listening on PORT 3000
[Object: null prototype] { name: 'Gourav', age: 12 }
```

## req.signedCookies

`req.signedCookies` 属性包含请求发送的已签名 cookie，未签名，并且在使用 `cookieParser()` 中间件时可以使用。对 cookie 进行签名不会使其隐藏或加密，而只是防止对 cookie 的篡改。它的工作原理是创建一个 HMAC 值（当前 cookie），然后 base64 对其进行编码。当 cookie 被读取时，它会重新计算签名，并确保它与附加到它的签名相匹配。如果不匹配，则给出一个错误。如果没有发送签名的 cookies，则属性默认为 `{}`。

### 示例

```js
var cookieParser = require('cookie-parser');
var express = require('express');
var app = express();
var PORT = 3000;

app.use(cookieParser());

app.get('/user', function (req, res) {
    // Setting multiple cookies
    req.signedCookies.title = 'Gourav';
    req.signedCookies.age = 12;

    console.log(req.signedCookies);
    res.send();
});

app.listen(PORT, function(err){
    if (err) console.log(err);
    console.log("Server listening on PORT", PORT);
});
```

### 输出

现在打开浏览器，向 `http://localhost:3000/user` 发出 GET 请求，现在可以在控制台上看到如下输出：

```js
Server listening on PORT 3000
[Object: null prototype] { title: 'Gourav', age: 12 }
```

## req.cookies 与 req.signedCookies 的区别

| req.cookies | req.signedCookies |
| :--- | :--- |
| 我们无法识别返回的 cookie 数据是否已被客户端修改。 | 如果我们想确保返回给 cookie 的数据未被客户端修改，我们使用签名 cookie。 |
| 如果请求不包含 cookies，默认为 `{}`。 | 如果没有发送签名的 cookies，此属性默认为 `{}`。 |
| 服务器无法检测 cookie 是否已被客户端更改。 | 服务器可以检测 cookie 是否已被客户端更改。 |
| 未向 cookie 添加签名。 | 签名作为 cookie 的一部分与实际 cookie 数据一起添加。数据来自该签名 cookie 和仅服务器知道的密钥。 |