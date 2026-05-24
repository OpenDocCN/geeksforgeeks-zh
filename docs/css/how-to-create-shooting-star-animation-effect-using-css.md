# 如何使用 CSS 创建流星动画效果？

> 原文:[https://www . geeksforgeeks . org/如何创建-拍摄-明星-动画-效果-使用-css/](https://www.geeksforgeeks.org/how-to-create-shooting-star-animation-effect-using-css/)

流星效果是黑暗主题网站最酷的背景效果之一。流星动画是一个非凡的例子，它展示了一个加载屏幕，在相当长的时间内吸引你的眼球，让剩余的内容加载到网站上。这种效果可以用在页面加载器、UI 中。

**方法:**方法是使用 CSS 属性(如 webkit-transform 和 transform)做一个小的迂回并以 45 度对齐它们的运动，然后使用@关键帧和@-WebKit-关键帧属性为星尾和星头(闪亮部分)添加动画，现在为拍摄效果添加延迟。关于这三个属性的基本信息对于本文的进一步讨论至关重要。

**HTML 代码:**在本节中，我们将创建网页的基本设计。

## HTML

```html
<!DOCTYPE html>
<html>

<head>
    <title>Shooting Star Animation</title>
</head>

<body>
    <div class="sky">

        <!-- We are making divisions, every div.
        represent a single roundabout balls -->
        <div class="star"></div>
        <div class="star"></div>
        <div class="star"></div>
        <div class="star"></div>
        <div class="star"></div>
        <div class="star"></div>
        <div class="star"></div>
    </div>
</body>

</html>
```