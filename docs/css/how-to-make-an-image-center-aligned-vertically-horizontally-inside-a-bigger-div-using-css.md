# 如何使用 CSS 在一个更大的 div 中使图像居中对齐(垂直&水平)？

> 原文:[https://www . geeksforgeeks . org/如何制作图像-中心对齐-垂直-水平-在更大的 div 内-使用-css/](https://www.geeksforgeeks.org/how-to-make-an-image-center-aligned-vertically-horizontally-inside-a-bigger-div-using-css/)

在本文中，我们将了解如何使用 CSS 对 div 标签中的图像进行居中对齐&还将通过示例了解其实现。给定一个图像，我们需要在一个更大的 div 中设置与中心对齐(垂直和水平)的图像。可以使用元素的[位置属性](https://www.geeksforgeeks.org/css-positioning-elements/)来完成。

**示例 1:** 本示例使用**位置属性**使图像与中心对齐。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>Horizontal and Vertical alignment</title>

    <!-- Style to set horizontal and
        vertical alignment -->
    <style>
    #Outer {
        border: 2px solid black;
        height: 300px;
        position: relative;
    }

    img {
        position: absolute;
        margin: auto;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
    }
    </style>
</head>

<body>
    <div id="Outer">
        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20211101104133/1-300x139.png" />
    </div>
</body>

</html>
```

**输出:**

![](img/1b1577863df6bab8d1433dac21eea889.png)

**示例 2:** 本示例使用**中心属性**将图像设置为在 div 中居中。我们也可以使用这种方法将项目与中心对齐。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title> Horizontal and Vertical alignment </title>
    <style>
    #Outer {
        border: 2px solid black;
        height: 300px;
        background: url(
https://media.geeksforgeeks.org/wp-content/uploads/20211101104133/1-300x139.png)
          no-repeat center center;
    }
    </style>
</head>

<body>
    <div id="Outer"></div>
</body>

</html>
```

**输出:**从输出中我们可以看到输出和之前的输出是一样的。

![](img/1b1577863df6bab8d1433dac21eea889.png)