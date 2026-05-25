# 如何使用 HTML 和 CSS 创建图像手风琴？

> 原文:[https://www . geesforgeks . org/how-create-image-accordion-use-html-and-CSS/](https://www.geeksforgeeks.org/how-to-create-image-accordion-using-html-and-css/)

在本文中，我们将创建一个图像手风琴，它基本上用于使用 HTML 和 CSS 的电子商务网站上的广告目的。

## 方法

*   创建一个 HTML 文件，在其中添加不同类型的广告图片。
*   创建一个 CSS 样式，为网页元素提供一些动画效果。

## HTML 代码

1.  首先，创建一个 HTML 文件 (`index.html`)。
2.  HTML 文件创建后，我们将使用`<title>`标签为网页添加标题。它应放置在`<head>`标签内。
3.  然后链接提供所有动画效果的 CSS 文件。这也放置在`<head>`标签内。
4.  来到 HTML 代码的主体部分。
    1.  然后我们必须添加不同的广告。

## HTML

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" href="style.css">
</head>

<body>
    <div class="main_box">
        <div class="img img1">
            <p>gfg 1</p>
        </div>

<div class="img img2">
            <p>gfg 2</p>
        </div>

<div class="img img3">
            <p>gfg 3</p>
        </div>

<div class="img img4">
            <p>gfg 4</p>
        </div>
    </div>
</body>

</html>
```