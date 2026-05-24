# 如何使用 CSS 设置主体元素的背景图像？

> 原文:[https://www . geeksforgeeks . org/如何使用 css 为身体元素设置背景图像/](https://www.geeksforgeeks.org/how-to-set-background-image-for-the-body-element-using-css/)

在本文中，我们使用 CSS 属性将图像设置为背景。背景图像属性用于为元素设置一个或多个背景图像。默认情况下，它将图像放在左上角。要指定两个或多个图像，请用逗号分隔 URL。

**语法:**

```html
background-image: url("url");
```

**属性值:**保存想要作为背景图片的图片的 URL。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        How to set background-image for
        the body element using CSS ?
    </title>

    <style>
        body {
            background-image: url(
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/CSS.png");
            text-align: center;
        }
    </style>
</head>

<body>
    <h1 style="color: white;">
        GeeksforGeeks
    </h1>

    <h3>
        Set background-image for
        the body element
    </h3>
</body>

</html>
```

**输出:**

![](img/096fb5afdca4908d6eff5315a7bfe050.png)

**支持的浏览器:**

*   谷歌 Chrome 1.0
*   Edge 4.0
*   Firefox 1.0
*   歌剧 3.5
*   Safari 1.0