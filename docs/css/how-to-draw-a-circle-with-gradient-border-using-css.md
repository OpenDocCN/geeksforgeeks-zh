# 如何用 CSS 画一个有渐变边框的圆？

> 原文:[https://www . geeksforgeeks . org/如何使用-css/](https://www.geeksforgeeks.org/how-to-draw-a-circle-with-gradient-border-using-css/) 绘制带渐变边框的圆

CSS 用于创建各种不同颜色或渐变的形状和样式。在本文中，我们将学习如何绘制一个带有渐变边框的圆。

**方式:**我们要创建两个 div 一个是外 div 带类*外 _ 圆*另一个是内 div 带类*内 _ 圆*。外部 div 包含带有渐变颜色的大圆，内部 div 包含一个白色小圆，作为圆的内端，形成圆的边界。**线性渐变**是一个 CSS 函数，我们将使用它来设置一个线性渐变作为背景图像。

**语法:**

```html
 .class_name { background-image: linear-gradient(direction, color1, color2 } 
```

**参数:**该函数接受三个参数，如上所述，如下所述:

*   **$方向:**指定移动渐变的方向。
*   **$color1:** 指定第一个颜色停止。
*   **$color2:** 指定第二个颜色停止。

**程序:**我们可以用线性梯度函数画一个有梯度边界的圆，如下图所示:

```html
<!DOCTYPE html>
<html>

<head>
    <!-- CSS -->
    <style>
        .outer_circle {
            position: relative;
            margin: 50px;
            width: 100px;
            height: 100px;
            border-radius: 50%;
            background: #ffffff;
        }

        .inner_circle {
            background-image: linear-gradient(
                     to bottom, rgb(9, 112, 26) 0%,
                     rgb(21, 255, 0) 100%);
            content: '';
            position: absolute;
            top: -20px;
            bottom: -20px;
            right: -20px;
            left: -20px;
            z-index: -1;
            border-radius: inherit;
        }
    </style>
</head>

<body>
    <div class="outer_circle">
        <div class="inner_circle"></div>
    </div>
</body>

</html>
```

**输出:**
![](img/d6b452fa133a353277045600cf4c43f3.png)