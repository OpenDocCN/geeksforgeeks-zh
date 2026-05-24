# 如何使用 Vue.js 在悬停时用动画展开按钮？

> 原文:[https://www . geesforgeks . org/how-expand-button-with-animation-on-hover-using-vue-js/](https://www.geeksforgeeks.org/how-to-expand-button-with-animation-on-hover-using-vue-js/)

在本文中，我们将使用 HTML 和 CSS 创建一个简单的按钮。之后，我们将添加一些 vue.js 代码来制作鼠标悬停时的动画按钮。

为了制作按钮动画，我们首先创建一个按钮。我们将应用悬停。

**HTML 按钮代码:**

## HTML

```jshtml
<!DOCTYPE html>
<html>
<head>
    <link rel="stylesheet" href="style.css">
</head>

<body>
    <div id="app">
        <h1>GeeksForGeeks Button Animation</h1>
        <hr>
        <button :class="classes" 
            @mouseover="hoverOver" 
            @mouseout="hoverOut">
            This is Button
        </button>
    </div>
</body>
</html>
```