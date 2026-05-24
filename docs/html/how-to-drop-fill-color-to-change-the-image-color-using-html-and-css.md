# 如何使用 HTML 和 CSS 拖放填充颜色来改变图像颜色？

> 原文:[https://www . geesforgeks . org/如何使用 html 和 css 拖放填充颜色以更改图像颜色/](https://www.geeksforgeeks.org/how-to-drop-fill-color-to-change-the-image-color-using-html-and-css/)

在本文中，我们将使用 HTML & CSS 创建一个拖放填充颜色效果，其中当我们将鼠标悬停在图像上时，图像会被着色。当您将鼠标悬停在图像上时，会出现一滴颜色落在图像上，从而将图像的颜色从灰色变为彩色。

**方法:**

1.  Create an HTML file in which we add text and div to the image.
2.  Then we must use the hover attribute to color our image.
3.  In our project, we also use pseudo classes like:: before and:: after.
4.  Use the @ keyframe to move our water droplets.

**HTML 代码:**

*   First, create an HTML file (index.html).
*   Then link the CSS file that provides all animation effects to our HTML. Also placed in the section.
*   Come to the main part of our HTML code:
    *   First, we will create a main div.
    *   Then, we give the main div a class, and create another div within the current div, and put an image in it.

## HTML

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