# 在 HTML 文档中应用颜色的不同方式

> 原文:[https://www . geesforgeks . org/不同的方式在 html 文档中应用颜色/](https://www.geeksforgeeks.org/different-ways-to-apply-colors-in-an-html-document/)

多彩的网站或应用程序比黑白网站更有吸引力。在本文中，我们将介绍在 HTML 文档中应用颜色的所有不同方法。像其他 HTML 标签一样，在 HTML 文档中没有特殊的标签来应用颜色。但是，使用 [*样式*](https://www.geeksforgeeks.org/html-style-attribute/) 属性，可以让某个特定的元素变得丰富多彩且吸引人。我们还将讨论颜色编码方法，帮助您使用不同的方法应用相同的颜色。

在*样式*属性中有两个主要属性来设置文本的颜色和块的背景。

*   **Color:** Used to set the color of the text.
*   **Background color:** Used to set the background color of web pages, specific blocks or elements.

**例 1:** 我们可以用 [*文字*](https://www.geeksforgeeks.org/html-body-text-attribute/) 属性设置文字的颜色，用*[*BG-color*](https://www.geeksforgeeks.org/html-bgcolor-attribute/)设置背景颜色。*

## *HTML*

```html
*<!DOCTYPE html>
<html>

<head>
    <title>Set the text color</title>
</head>

<body>
    <h1 style="color:green"> 
        hello! Welcome to GFG 
    </h1>

    <h2 style="color:Red"> 
        hello! Welcome to GFG 
    </h2>

    <h3 style="background-color:Blue">
        hello! Welcome to GFG </h3>
    <h3 style="background-color:Blue; color:red">
        hello! Welcome to GFG </h3>
</body>

</html>*
```