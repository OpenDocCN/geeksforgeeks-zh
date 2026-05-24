# HTML | lang 属性

> 原文:[https://www.geeksforgeeks.org/html-lang-attribute/](https://www.geeksforgeeks.org/html-lang-attribute/)

该属性用于指定元素内容的语言。一些语言的例子是英语的 en，西班牙语的 es 等。

**语法:**

```html
<element lang = "language_code">
```

**属性值:**该属性包含单值*语言 _ 代码*，用于指定内容的语言。

**HTML 4.1 与 HTML 5 的区别:**在 HTML 5 中，lang 属性可以与任何 HTML 元素一起使用，但在 HTML 4.1 中，lang 属性与< base >、< br >、< frame >、< frameset >、< hr >、< iframe >、< param >和< script >元素一起使用。

**示例:**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>lang attribute</title>
        <style>
            body {
                text-align:center;
            }
            h1 {
                color:green;
            }
        </style>
    </head>
    <body>
        <h1>GeeksforGeeks</h1>
        <h2>lang attribute</h2>

        <p lang = "en">A computer science portal for geeks</p>
    </body>
</html>
```

**输出:**
![](img/055f9e25c9bb6bb4995e191519eec438.png)

**支持的浏览器:**郎属性支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队