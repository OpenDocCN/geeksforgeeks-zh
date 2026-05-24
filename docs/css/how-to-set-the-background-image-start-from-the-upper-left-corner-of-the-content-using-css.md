# 如何使用 CSS 设置背景图像从内容左上角开始？

> 原文:[https://www . geesforgeks . org/如何设置背景图片-从左上角开始-内容-使用-css/](https://www.geeksforgeeks.org/how-to-set-the-background-image-start-from-the-upper-left-corner-of-the-content-using-css/)

在本文中，我们将学习如何使用 CSS 从内容的左上角开始设置背景图像。

**方法:**我们使用 CSS 的 [**背景图像**](https://www.geeksforgeeks.org/css-background-image-property/) 属性来设置背景图像。为了放在左上角，我们将使用 [**背景-原点**](https://www.geeksforgeeks.org/css-background-origin-property/) 属性来调整网页的背景图像。所以设置背景图像从内容的左上角开始，我们将背景原点属性值设置为边框或填充框。

**语法:**

```html
background-origin: border-box | padding-box
```

**示例 1:**

## HTML

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Document</title>
    <style>
      .gfg {
        width: 60%;
        border: 8px solid red;
        padding: 200px;
        background-image: url(
"https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-12.png");
        background-repeat: no-repeat;
        background-origin: padding-box;
      }
    </style>
  </head>
  <body>
    <div class="gfg"></div>
  </body>
</html>
/sourcecode]
```