# 使用 cURL Set-1 发送 HTTP 请求

> 原文:[https://www . geesforgeks . org/sending-http-request-use-curl-set-1/](https://www.geeksforgeeks.org/sending-http-request-using-curl-set-1/)

每当我们处理 HTTP 请求时， [cURL](https://www.geeksforgeeks.org/curl-command-in-linux-with-examples/) 在很大程度上简化了我们的任务，是最容易染指的工具。

[**【cURL:**](https://curl.se/)它代表“客户端 URL”，用于命令行或脚本中传输数据。它是处理 [HTTP 请求](https://www.geeksforgeeks.org/http-get-post-methods-php/)的一个很好的工具，比如 GET、POST、PUT、DELETE 等等。虽然它为我们提供了其他互联网协议的支持，如 HTTPS、FTP、SMTP、TELNET，但在本文中，我们将仅限于 HTTP。

**先决条件:** [根据您的底层操作系统正确安装 cURL](https://curl.se/download.html) 。

要检查它是否安装在您的系统中或了解其版本，请在命令提示符下执行以下命令

**语法:**

```html
 curl --version
```

**输出:**

> curl 7 . 67 . 0(x86 _ 64-PC-Linux-GNU)libcurl/7 . 67 . 0 OpenSSL/1 . 1 . 1d zlib/1 . 2 . 11
> brot Li/1 . 0 . 7 libid N2/2 . 2 . 0 libp sl/0 . 20 . 2(+libid N2/2 . 0 . 5)libs H2/1 . 8 . 0 nghttp2/1 . 41 . 0 librtmp/2.3
> 发布日期:2011 年

我们可以看到，当使用*–版本*标志时，输出显示了版本、发布日期、协议和 curl 的其他特性。

**注意:**输出可能因版本和底层操作系统而异。

**使用 cURL 的 GET 请求:** Get 请求是最常用的 HTTP 请求，因为它用于从服务器请求关于特定目标(即网站)的数据。让我们从执行一个简单的获取请求开始。

```html
 curl http://138.68.158.87:30954/login.php
```

请注意，您可以指定您想要请求数据的目标，而不是*http://138.68.158.87:30954/login.php,。*

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <link rel="stylesheet" href="./style.css">
</head>

<body>
    <hgroup>
        <h1>Admin panel</h1>
    </hgroup>

    <form action="" method="post">
        <div class="group">
            <input name="username" type="text">
            <span class="highlight"></span>
            <span class="bar"></span>
            <label>Username</label>
        </div>

        <div class="group">
            <input name="password" type="password">
            <span class="highlight"></span>
            <span class="bar"></span>
            <label>Password</label>
        </div>

        <button type="submit" class="button buttonBlue">
            Login
            <div class="ripples buttonRipples">
                <span class="ripplesCircle"></span>
            </div>
        </button>
    </form>

    <script src=
'https://cdnjs.cloudflare.com/ajax/libs/jquery/2.1.3/jquery.min.js'>
    </script>

    <script src="./script.js"></script>
</body>

</html>
```

通过这种方式，您将获得整个输出，如果您通过浏览器的查询和来自服务器的响应由客户端浏览器呈现，然后以简化的方式显示给您，则整个输出将是相同的。

**注意:**如果查看目标源代码，会发现同样的输出。

上面的查询可以使用许多其他标志。

*   **-v:** 用于获取详细输出。

```html
curl http://138.68.158.87:30954/login.php -v
```

*   **-u:** 服务器用户和密码。

```html
 curl -u username:password http://138.68.158.87:30954/login.php -v
```

*   **-L:** 跟随重定向。

```html
curl -u username:password -L http://138.68.158.87:30954/login.php -v
```

*   **-X:** 指定要使用的请求命令。

```html
curl -X GET http://138.68.158.87:30954/login.php -v
```

**注意:**如果我们没有指定请求命令，默认情况下 curl 使用 GET 请求。

*   **-s:** 静音模式。

```html
curl -u username:password -s -L http://138.68.158.87:30954/login.php -v
```

借助 **-h** 标志，您可以根据需要深入使用不同的标志。

```html
curl -h
```