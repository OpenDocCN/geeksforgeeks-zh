# 使用 HTML 和 CSS 的跳舞键效果

> 原文:[https://www . geesforgeks . org/dancing-key-effect-use-html-and-CSS/](https://www.geeksforgeeks.org/dancing-keys-effect-using-html-and-css/)

跳舞键效果是一种文本动画效果，可以使用 CSS 实现。在这种效果下，每个字母都以键盘键的形式给出，然后应用动画使其沿 X 轴或 Y 轴移动。这种效果也称为跳跃键效果或钢琴键效果。一般用在教育网站上，让孩子的学习变得有趣和互动。

**方法:**方法是首先使用一些基本样式设计关键点，然后使用[关键帧](https://www.geeksforgeeks.org/css-keyframes-rule/)沿任意一个轴设置关键点的动画。**第 n 个子**属性也可以用来分别延迟每个关键点的动画。如果不希望按键之间有任何延迟，此步骤是可选的。

**HTML 代码:**在这个 HTML 部分，所有的字母都被包装在< span >标签里面，而这个标签又被包装在一个< h1 >标签里面。

## HTML

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>
        DANCING KEY EFFECT
    </title>
</head>

<body>
    <h1>
        <span>G</span>
        <span>E</span>
        <span>E</span>
        <span>K</span>
        <span>S</span>
        <span>F</span>
        <span>O</span>
        <span>R</span>
        <span>G</span>
        <span>E</span>
        <span>E</span>
        <span>K</span>
        <span>S</span>
    </h1>
</body>

</html>
```