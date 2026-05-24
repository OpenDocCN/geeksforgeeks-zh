# 如何在项目中使用 jQuery 库？

> 原文:[https://www . geeksforgeeks . org/如何使用-a-jquery-项目中的库/](https://www.geeksforgeeks.org/how-to-use-a-jquery-library-in-your-project/)

在本文中，我们将看到如何在项目中使用 jQuery 库。在项目中添加 jQuery 库有两种方法，它们是–

*   包含来自 CDN 链接的 jQuery 库
*   从官网下载 jQuery 库

**包含来自 CDN 链接的 jQuery 库:** CDN 代表内容交付网络，基本上是一套用于存储和交付数据的服务器。基本上，这些 jQuery 库文件已经上传到各种 cdn，我们可以直接在网页上使用它们。然后，我们不需要在本地机器上下载任何文件。

我们可以在“src”属性中看到 CDN 链接。我们已经成功地将 jQuery 添加到我们的网页中。我们可以在页面上使用 jQuery 的所有功能。加载页面时，浏览器会自动从 CDN 链接下载 jQuery 库文件。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content=
        "width=device-width, initial-scale=1.0">

    <!-- Including jQuery -->
    <script src="
https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>
</head>

<body style="text-align: center;">
    <h1 style="color: green;">
        GeeksforGeeks
    </h1>

    <h3>
        Include jQuery library from CDN link
    </h3>

    <h2>Welcome to GeeksforGeeks</h2>

    <button id="id_attr">Add Style</button>

    <script>
        $(document).ready(function() {
            $('#id_attr').click(function() {
                $('h2').css("color", "green");
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/f5830169e6b3edaee406844598df4b19.png)

**下载 jQuery 库:**在本节中，我们首先从[可下载链接](https://jquery.com/download/)下载 jQuery 库。下载完文件后，我们将以这种方式将下载的文件添加到我们的网页中。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content=
        "width=device-width, initial-scale=1.0">

    <!-- Including jQuery -->
    <script src="jquery-3.6.0.js">
    </script>
</head>

<body style="text-align: center;">
    <h1 style="color: green;">
        GeeksforGeeks
    </h1>

    <h3>
        Download the jQuery library
    </h3>

    <h2>Welcome to GeeksforGeeks</h2>

    <button id="id_attr">Add Style</button>

    <script>
        $(document).ready(function() {
            $('#id_attr').click(function() {
                $('h2').css("color", "green");
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/e9b05589afd5849139004f14d15fd6b3.png)