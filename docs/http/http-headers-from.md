# HTTP 头|来自

> 原文:[https://www.geeksforgeeks.org/http-headers-from/](https://www.geeksforgeeks.org/http-headers-from/)

**HTTP From 标头**是请求类型标头，它指示通过机器人代理发送给客户端的电子邮件地址。该代理将是由主用户运行的爬虫或用户机器人代理。标题字段包含请求用户代理的用户或客户端的互联网电子邮件地址。主要优点是，如果机器人代理向客户端发送不需要的请求，则可以联系到主用户。“发件人”标题字段可以有许多用途，如记录日志，也可以作为调查人员了解过多请求的来源。出于安全考虑，发件人标题中使用的电子邮件地址应该不同于主机标题。

**语法:**

```html
From: <email>
```

**指令:**此标题接受一个如上所述的指令，如下所述

*   **< E-mail >:** This command represents an available e-mail address of a machine.

**注意:**最好不要将其用于认证或验证过程示例:

**例:**

```html
From: careers@geeksforgeeks.org
```

```html
From: no-reply-contribute@geeksforgeeks.org
```

**支持的浏览器:**以下列出 **HTTP 表单头**支持的浏览器: