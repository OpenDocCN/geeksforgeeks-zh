# HTML 中跨原点属性的目的是什么？

> 原文:[https://www . geeksforgeeks . org/html 中跨来源属性的目的是什么/](https://www.geeksforgeeks.org/what-is-the-purpose-of-crossorigin-attribute-in-html/)

正如我们所知，HTML 引入了许多元素和属性，这些元素和属性有一些定义和规范，将用于增强 web 开发。在本文中，我们将学习如何在 HTML 中使用 crossorigin 属性。

crossorigin 属性的目的是用于将资源从一个域共享到另一个域。基本上，它用于处理 CORS 请求。它用于处理 CORS 请求，检查允许共享来自其他域的资源是否安全。这些资源可能包括音频、视频、图像、链接或指定是否支持跨来源请求的外部脚本。

**CORS:** 代表跨产地资源共享。它是一种机制，通过这种机制，一个网页请求另一个域来获取资源，如音频、视频、脚本等。而不会泄露他们的凭证信息。

**值:**该属性包含两个值，如下所示–

*   **匿名:**有默认值。它定义了一个 CORS 请求，该请求将在不传递凭据信息的情况下发送。
*   **使用-凭证:**跨来源请求将与凭证、cookies 和证书一起发送。

**示例:**下面的代码演示了在<脚本>元素中使用 crossorigin 属性。

## index.html

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        What is the purpose of crossorigin 
        Attribute in HTML?
    </title>
</head>

<body style="text-align: center">
    <h1>GeeksForGeeks</h1>

    <h2>
        What is the purpose of 
        crossorigin Attribute in HTML?
    </h2>

    <script id="myGeeks" type="text/javascript" 
        src="my_script.js" crossorigin="anonymous">
    </script>
    <br />

    <button>
        Submit
    </button>
</body>

</html>
```

## 我的 sctipt.js

```html
alert("Hello GeeksForGeeks")
```

**输出:**

![](img/b9a3838fff30658a2e434ef9c145ff1f.png)