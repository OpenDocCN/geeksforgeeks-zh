# 如何用 CSS 为按钮制作边框弹出动画？

> 原文:[https://www . geeksforgeeks . org/如何使用 css 制作按钮边框弹出动画/](https://www.geeksforgeeks.org/how-to-make-border-popup-animation-for-buttons-using-css/)

在本文中，我们将学习如何为您的网站按钮制作边框弹出动画。为了创建边框弹出动画，我们使用 [CSS 伪元素](https://www.geeksforgeeks.org/css-pseudo-elements/)。

CSS 伪元素是添加到选择器中的关键字，它允许您设置所选元素的特定部分的样式。为了制作这样的动画，我们需要把我们的网站制作得看起来体面，这样客户就可以留在网站上。

**示例:**

## HTML

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content=
        "width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <link rel="stylesheet" href="styles.css">
</head>

<body>
    <button class="btn btn-border-pop">
        Border Pop
    </button>
</body>

</html>
```