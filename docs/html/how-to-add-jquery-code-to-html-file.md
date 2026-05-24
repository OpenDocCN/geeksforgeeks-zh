# 如何在 HTML 文件中添加 jQuery 代码？

> 原文:[https://www . geesforgeks . org/how-add-jquery-code-to-html-file/](https://www.geeksforgeeks.org/how-to-add-jquery-code-to-html-file/)

在本文中，我们将看到如何向 HTML 文件中添加 jQuery 代码。您可以使用多种方法轻松地将 [jQuery 添加到 HTML](https://www.geeksforgeeks.org/most-efficient-way-to-create-html-elements-using-jquery/) 中，例如从 CDN 添加 jQuery 或直接下载 jQuery 文件并将其包含到您的项目中。本文讨论了几种方法。

**方法:**

*   下载并包含 jQuery 文件
*   包括来自 CDN 的 jQuery。

**方法 1:** 下载并包含 jQuery 文件

按照下面的信息将 jQuery 包含在您的 HTML 文件中。

1.  使用此[链接](https://jquery.com/download/)从 JQuery 官方网站下载 jQuery 文件。(根据需要下载压缩或未压缩的文件)。
2.  下载后，只需将下载的文件移动到您想要添加 jQuery 的 HTML 文件中。
3.  最后，使用下面的语法在 HTML 文件中包含 jQuery。即在脚本标签之间添加 jQuery 文件名。

```html
<script type="text/javascript" src="jquery-3.5.1.min.js"> </script>
```

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
  <head>
    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js">
    </script>
    <script>
      $(document).ready(function () {
        $("button").click(function () {
          $("h2").html("Complete Portal for Geeks</b>");
        });
      });
    </script>
  </head>
  <body>
    <center>
      <h2>GeeksforGeeks</h2>
      <button>Click here</button>
    </center>
  </body>
</html>
```

**输出:**

![](img/92ad6be4c89213e0b8ff13d55fb6fa31.png)

**方法 2:** 按照下面的步骤在 HTML 文件中包含 Jquery。

1.  在这种情况下，您只需要将下面带有脚本标签的链接添加到您的 HTML 文件中，无论是谷歌还是微软提供的 CDN。
    *   谷歌 CDN

    *   微软 CDN

示例:

## 超文本标记语言

```html
<html>
  <head>
    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>
    <title>Added Jquery into HTML</title>

    <style>
      h1 {
        color: green;
      }
    </style>
  </head>

  <body>
    <center>
      <h1>Welcome to GeeksforGeeks</h1>
      <button id="trigger">Click me</button>
      <h3 id="demo"></h3>

      <script type="text/javascript">
        $(document).ready(function () {
          $("#trigger").click(function () {
            $("#demo").html("Complete portal for Geeks");
          });
        });
      </script>
    </center>
  </body>
</html>
```

**输出:**

![](img/a62dfc20d012108cedf9cd4629e82426.png)