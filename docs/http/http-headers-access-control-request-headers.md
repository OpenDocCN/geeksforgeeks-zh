# HTTP 头|访问控制请求头

> 原文:[https://www . geesforgeks . org/http-headers-access-control-request-headers/](https://www.geeksforgeeks.org/http-headers-access-control-request-headers/)

**访问控制请求头**是浏览器使用的请求类型头，包含客户端将在后续请求中发送的不同 HTTP 头的信息。每当客户端向服务器发起请求时，浏览器都会检查该请求是否需要 CORS 飞行前检查。如果需要 CORS 飞行前请求，浏览器使用 HTTP Options 方法发送一个请求，该请求附有一堆标题，其中包含有关后续请求的某些特征的信息。这些特征之一是请求可能包含不同的头。该信息存储在预检请求的访问控制请求头中。

**语法:**

```html
Access-Control-Request-Headers: header-name-1, header-name-2, ...
```

**指令:**访问控制-请求-标题头接受一个指令，如上所述，如下所述:

*   **标题名称:**逗号分隔的标题名称列表，将附加到后续请求中。

下面的例子说明了 http 头中的**访问控制请求头**。
**示例:**考虑以下代码从浏览器发送 XHR 请求。

```html
const xhr = new XMLHttpRequest();

xhr.open('POST', 'https://samplepostroute/');
xhr.setRequestHeader('X-PINGOTHER', 'pingpong');
xhr.setRequestHeader('Content-Type',
           'application/x-www-form-urlencoded');
xhr.onreadystatechange = handler;

xhr.send("id=100"); 

```

该请求将包含内容类型和 X-PINGOTHER HTTP 头。在发送开机自检请求之前，浏览器将发送 CORS 预检请求。CORS 预检请求将包含以下标题。以这种方式，服务器被告知在随后的客户端请求中可能存在的不同报头。

```html
Access-Control-Request-Headers: X-PINGOTHER, Content-Type
```

**支持的浏览器:**以下浏览器与访问控制请求标题功能兼容:

*   谷歌 Chrome 4.0
*   火狐浏览器 3.5
*   Internet Explorer 10.0
*   Opera 12.0
*   Safari 4.0