# 如何使用 CSS 创建动画模糊导航条？

> 原文:[https://www . geesforgeks . org/如何创建-动画-模糊-nav bar-使用-css/](https://www.geeksforgeeks.org/how-to-create-animated-blur-navbar-using-css/)

导航栏是任何网站的主要组件，用户可以通过它浏览网站的所有组件和部分。这就是为什么拥有一个设计良好的导航栏或菜单非常重要。所以今天我们将看到一个导航条，其中除了悬停元素外，所有元素都变得模糊。

**方法:**方法是使用[模糊()](https://www.geeksforgeeks.org/css-blur-function/)功能和[悬停](https://www.geeksforgeeks.org/css-hover-selector/)选择器来模糊除悬停元素之外的所有元素。

**HTML 代码:**这里，我们创建了一个简单的无序列表，包含 3 个列表项。

## HTML

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, initial-scale=1.0">
    <title>Blurred Menu Design</title>
</head>
<body>
    <ul>
        <li>Home</li>
        <li>About</li>
        <li>Contact Us</li>
    </ul>
</body>
</html>
```