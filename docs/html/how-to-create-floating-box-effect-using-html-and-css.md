# 如何用 HTML 和 CSS 创建浮箱效果？

> 原文:[https://www . geesforgeks . org/如何使用 html 和 css 创建浮动框效果/](https://www.geeksforgeeks.org/how-to-create-floating-box-effect-using-html-and-css/)

浮动框效果是自定义框阴影技术的经典示例。在这种技术中，我们创建看起来逼真的阴影，而不使用 CSS 提供的盒子阴影属性。

**方法:**方法是在选择器之后使用[使用](https://www.geeksforgeeks.org/css-after-selector/)[模糊](https://www.geeksforgeeks.org/css-blur-function/)功能创建阴影。

**HTML 代码:**在本节中，我们已经创建了身体的基本结构。这里，我们使用了一个包含类属性的< div >标签来渲染屏幕上的浮动框。

## HTML

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width,
                   initial-scale=1.0">
    <title>Floating Box</title>
</head>
<body>
    <h1>GeeksForGeeks</h1>
    <div class="geeks"></div>
</body>
</html>
```