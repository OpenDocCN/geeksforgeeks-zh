# 如何使用 jQuery 构建简单的终端类网站？

> 原文:[https://www . geeksforgeeks . org/如何使用-jquery/](https://www.geeksforgeeks.org/how-to-build-simple-terminal-like-website-using-jquery/) 构建类似简单终端的网站

终端是开发者最常用的工具之一。许多应用程序、框架，甚至编程语言都有更多可以使用命令行界面调用的功能。大多数计算机的操作系统中至少有一个带有命令提示符的终端，现在大多数被 windows 中的跨平台 powershell 和基于 Linux 的操作系统中的 Linux 控制台所取代。

到目前为止，你们大多数人都已经将终端理解为系统应用程序，但是我们如何在浏览器中构建像网站一样的终端呢？为此 **JavaScript** 得到了我们的支持，这些终端喜欢并感觉像是系统终端，但没有它们强大，但它们为我们做了工作，感谢一些开发人员，我们得到了一些库来帮助我们，而不是从头开始写。一些库是 **jQuery.terminal，Xtermjs，**在本教程中我们将使用 jQuery.terminal

现在打开你最喜欢的代码编辑器，创建我们的基本 html 文件大部分是 index.html，并调用我们的依赖关系

## HTML

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <!--content type : HTML -->
    <meta http-equiv="content-type" 
        content="text/html; charset=UTF-8">

    <!-- Making viewport responsive -->
    <meta name="viewport" content=
        "width=device-width,minimum-scale=1,
        initial-scale=1">

    <!-- Loading jQuery, jQuery.terminal, 
        and style sheet -->
    <script src=
        "https://code.jquery.com/jquery-3.3.1.min.js">
    </script>

    <script src=
"https://unpkg.com/jquery.terminal/js/jquery.terminal.min.js">
    </script>

    <link rel="stylesheet" href=
"https://unpkg.com/jquery.terminal/css/jquery.terminal.min.css" />
</head>

<body>
</body>

</html>
```