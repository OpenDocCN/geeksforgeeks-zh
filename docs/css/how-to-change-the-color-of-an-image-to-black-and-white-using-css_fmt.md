# 如何使用 CSS 将图像的颜色改为黑白？

> 原文：[https://www.geeksforgeeks.org/how-to-change-the-color-of-an-image-to-black-and-white-using-css/](https://www.geeksforgeeks.org/how-to-change-the-color-of-an-image-to-black-and-white-using-css/)

本文的方法是使用 CSS 中的`filter`属性将图像的颜色更改为黑白。它用于设置元素的视觉效果。此属性主要用于图像内容。

基本上我们使用`grayscale()`方法将元素颜色转换成黑白。`grayscale(0%)`表示原始元素，`grayscale(100%)`表示完全灰度元素。

**语法：**

```css
filter: grayscale(100%)
```

## HTML 示例

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        How to change the color of an images 
        to black and white using CSS?
    </title>

    <style>
        .gfg {
            -webkit-filter: grayscale(100%);
            filter: grayscale(100%);
        }
    </style>
</head>

<body>
    <h2>GeeksForGeeks</h2>

    <h2>
        How to change the color of an images 
        to black and white using CSS?
    </h2>

    <img src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/20191121162913/s11.png">
    <br>

    <b>After Convert to Black and White</b> <br>
    <img class="gfg" src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/20191121162913/s11.png">
</body>

</html>
```

**输出：**

![](img/7da4cfc2f06508cddb00124405ffb2ba.png)