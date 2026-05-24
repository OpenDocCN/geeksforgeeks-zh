# 在网页中包含 jQuery 的不同方式

> 原文:[https://www . geeksforgeeks . org/differential-to-include-jquery-in-a-网页/](https://www.geeksforgeeks.org/different-ways-to-include-jquery-in-a-webpage/)

在本文中，我们将学习在页面中包含 jQuery 的不同方法。基本上，我们知道 jQuery 有很多令人兴奋的特性。因此，如果我们想使用这些功能，我们只需将 jQuery 库添加到我们的网页中。

有两种方法可以将 jQuery 库添加到我们的网页。

*   包含来自内容交付网络的 jQuery
*   从官网下载 jQuery 库

**1。包括来自 CDN Link 的 jQuery:****CDN**代表内容交付网络，它基本上是一套用于存储和交付数据的服务器。基本上，这些 jQuery 库文件已经上传到各种 cdn，我们可以直接在网页上使用它们。然后，我们不需要在本地机器上下载任何文件。

我们可以在“src”属性中看到 CDN 链接。我们已经成功地将 jQuery 添加到我们的网页中。我们可以在页面上使用 jQuery 的所有功能。加载页面时，浏览器会自动从 CDN 链接下载 jQuery 库文件。

**示例 1:** 在本例中，我们将添加 jQuery CDN 链接来执行 jQuery 代码。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <!-- jQuery library -->
    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.6.0/jquery.min.js">
    </script>
</head>

<body>
    <p></p>

    <script>
        $('p').text('Hello geeks. CDN Working');
    </script>
</body>

</html>
```

**输出:**

![](img/e9a7fdf125940e5889e7348a89569413.png)

**2。下载 jQuery 库:**这样，我们就可以在页面中添加 jQuery 库了。首先，我们将从 [jQuery](https://jquery.com/download/) 网站下载 jQuery 库文件到本地主机。下载后，我们将以这种方式将下载的文件添加到我们的网页中。

```html
<script src="file_name_with_full_path"></script>
```

**示例 2:** 在本例中，我们将从下载的路径添加 jQuery 链接来执行 jQuery 代码。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <!-- jQuery library -->
    <script src="jquery-3.6.0.js"></script>
</head>

<body>
    <p></p>

    <script>
        $('p').text('Hello geeks. Downloaded files');
    </script>
</body>

</html>
```

**输出:**

![](img/f6b4075c426af921f2c0f67fce3a061a.png)

在上面的例子中，网页和 jQuery 库文件都在同一个文件夹中。