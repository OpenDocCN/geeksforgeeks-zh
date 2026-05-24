# jQuery 手机简介

> 原文:[https://www.geeksforgeeks.org/jquery-mobile-introduction/](https://www.geeksforgeeks.org/jquery-mobile-introduction/)

jQuery Mobile 是一个基于 HTML5 的用户界面系统，旨在使所有智能手机、平板电脑和桌面设备都可以访问响应迅速的网站和应用程序。

jQuery mobile 框架将“少写多做”的口头禅更上一层楼:jQuery Mobile 框架不需要为每个移动设备或操作系统编写独特的应用程序，而是允许您设计一个单一的高品牌响应网站或应用程序，可以在所有流行的智能手机、平板电脑和桌面平台上运行。

![](img/9ff7df8c216c1618cdf819afc8cf0647.png)

#### jQuery Mobile 的特性:

*   它基于“少写多做”的口头禅。
*   用于制作响应性网站和应用程序。
*   它是开源的，并且是跨平台兼容的框架。
*   它利用 jQuery 和 jQuery UI 的特性来制作手机兼容的网站。

#### 如何使用？

我们可以通过两种方式将 jQuery Mobile 添加到项目中:

*   下载包文件
*   使用 CDN 链接

**下载包:**当你打开 jQuery mobile 的主网站即 jquerymobile.com/,时，你会看到有两个选项可以下载 jQuery Mobile 库。

1.  **自定义下载**—该选项用于下载库的自定义版本。
2.  **最新稳定**—此选项用于获取 jQuery 移动库的稳定最新版本。

![](img/d361959449ea298571ecefeab5a0f827.png)

**使用 CDN 链接:**我们需要包含三个 CDN 链接，以便将 jQuery Mobile 包含到我们的项目中。这三个链接用于:

*   包括 jQuery 移动样式表
*   包括 jQuery 库
*   包括 jQuery 移动库

> <link rel="”stylesheet”" href="”http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css”">
> <脚本 src = " http://code . jquery . com/jquery-1 . 11 . 1 . min . js "></脚本>
> <脚本 src = " http://code . jquery . com/mobile/1 . 4 . 5/jquery . mobile-1 . 4 . 5 . min . js "></脚本>

**示例:**这是一个使用一些 jQuery Mobile 类的网站的基本示例。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <meta name="viewport" content=
        "width = device-width, initial-scale = 1">
    <link rel="stylesheet" href=
"https://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css">
    <script src=
        "https://code.jquery.com/jquery-1.11.3.min.js">
    </script>
    <script src=
"https://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.js">
    </script>
</head>

<body>
    <div data-role="page" id="pageone">
        <div data-role="header">
            <h1>Hello Geeks!</h1>
        </div>

        <div data-role="main" class="ui-content">
            <h2> Welcome to GeeksforGeeks</h2>
        </div>

        <div data-role="footer">
            <p>Hope you have a great day!</p>
        </div>
    </div>
</body>

</html>
```

**输出:**

![](img/c2b50b9b92553f5a08938279dc9212cf.png)