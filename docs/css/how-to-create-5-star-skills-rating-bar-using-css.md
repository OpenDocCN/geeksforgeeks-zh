# 如何使用 CSS 创建 5 星技能等级栏？

> 原文:[https://www . geesforgeks . org/如何创建-5 星-技能-评级-条-使用-css/](https://www.geeksforgeeks.org/how-to-create-5-star-skills-rating-bar-using-css/)

在本文中，我们将使用 [CSS](https://www.geeksforgeeks.org/css-tutorials/) 和 [HTML](https://www.geeksforgeeks.org/html-tutorials/) 创建一个 5 星评级栏。五星评级栏用于收集用户意见或反馈。用户可以根据自己的满意度给出 5 分的评分。我们将创建评级栏的布局或设计。

**进场:**

*   对于星形图标，我们使用[字体-令人敬畏的](https://www.geeksforgeeks.org/css-icons/)图标库。
*   使用 HTML 创建布局。
*   对于样式，使用 CSS 属性。

**CSS 库:**要使用 Font Awesome Icons，我们必须使用链接标签在 HTML 文件中添加库。

> <link href="”https://pro.fontawesome.com/releases/v5.10.0/css/all.css”" rel="”stylesheet”/">

通过添加链接，我们可以访问这个库提供的图标。你可以在 [Font-Awesome](https://fontawesome.com/) 网站上获得自己项目的链接，也可以使用我们上面提到的相同链接。

**语法:**要使用星形图标，请使用以下语法。

```html
<i class="fas fa-star"></i>
```

**注:**请参考 [CSS 图标](https://www.geeksforgeeks.org/css-icons/)文章，以便更好的理解。

**示例:**我们使用上述方法创建了一个 5 星评级栏。我们添加了一个类*点击图标标签中的*。这个类用来改变星星的颜色。我们已经在[风格](https://www.geeksforgeeks.org/html-style-tag/)标签中添加了 CSS 属性。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>Rating Bar</title>
    <link href=
"https://pro.fontawesome.com/releases/v5.10.0/css/all.css"
        rel="stylesheet" />

    <style>
        .rating {
            font-size: 40px;
        }

        .clicked {
            color: rgb(135, 187, 32);
        }
    </style>
</head>

<body>
    <h1>5 Star Rating Bar</h1>
    <div class="rating">
        <i class="fa fa-star clicked"></i>
        <i class="fa fa-star clicked"></i>
        <i class="fa fa-star clicked"></i>
        <i class="fa fa-star clicked"></i>
        <i class="fa fa-star"></i>
    </div>
</body>

</html>
```

**输出:**

![](img/ae9ffe262dda1c1a831082a811ec1573.png)

使用 CSS 的 5 星级评定栏