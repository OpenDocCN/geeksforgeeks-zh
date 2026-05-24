# HTTP 头|访问控制-允许-方法

> 原文:[https://www . geesforgeks . org/http-headers-access-control-allow-methods/](https://www.geeksforgeeks.org/http-headers-access-control-allow-methods/)

**访问控制允许方法**头是跨来源资源共享(CORS)响应类型头。它用于指示在响应跨来源请求访问资源时允许哪些 HTTP 方法。

**语法:**

```html
Access-Control-Allow-Methods: <method>, <method>, ...

```

运筹学

```html
Access-Control-Allow-Methods: *

```

**指令:**该标题接受两个指令，如上所述，如下所述:

*   **<方法> :** 该指令由逗号分隔的 HTTP 请求方法列表组成。
*   ***:** 该指令是一个通配符值，用于指示所有缺少凭证(如 HTTP cookies 或 HTTP 身份验证信息)的请求。

**示例:**

```html
Access-Control-Allow-Methods: POST, GET, OPTIONS 

```

```html
Access-Control-Allow-Methods: *

```

**支持的浏览器:**浏览器兼容 **HTTP 访问控制允许方法**标题如下:

*   谷歌 Chrome
*   边缘
*   歌剧
*   火狐浏览器