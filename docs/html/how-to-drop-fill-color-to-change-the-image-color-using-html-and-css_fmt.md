# 如何使用 HTML 和 CSS 拖放填充颜色来改变图像颜色？

> 原文：[https://www.geeksforgeeks.org/how-to-drop-fill-color-to-change-the-image-color-using-html-and-css/](https://www.geeksforgeeks.org/how-to-drop-fill-color-to-change-the-image-color-using-html-and-css/)

在本文中，我们将使用 HTML & CSS 创建一个拖放填充颜色效果，其中当我们将鼠标悬停在图像上时，图像会被着色。当您将鼠标悬停在图像上时，会出现一滴颜色落在图像上，从而将图像的颜色从灰色变为彩色。

## 方法

1.  创建一个 HTML 文件，在其中添加文本和图像的 `div`。
2.  然后我们必须使用 `hover` 属性来为图像着色。
3.  在我们的项目中，我们还使用了伪类，如 `::before` 和 `::after`。
4.  使用 `@keyframes` 来移动我们的水滴。

## HTML

*   首先，创建一个 HTML 文件 (`index.html`)。
*   然后链接提供所有动画效果的 CSS 文件 (`style.css`) 到我们的 HTML。同样放在 `<head>` 部分。
*   来到我们 HTML 代码的主要部分：
    *   首先，我们将创建一个主 `div`。
    *   然后，我们给主 `div` 一个类，并在当前 `div` 内创建另一个 `div`，并在其中放入一张图片。

```html
<!DOCTYPE html>
<html lang="en">

<head>

<link rel="stylesheet" href="style.css">
</head>

<body>
    <h1>
        hover over the icon to
        get the icon colored
    </h1>

<div class="main_box">
        <div class="img"></div>
    </div>
</body>

</html>
```