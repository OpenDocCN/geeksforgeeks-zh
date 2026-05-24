# 如何使用 HTML CSS 和 jQuery 创建 followspot 效果？

> 原文:[https://www . geesforgeks . org/how-create-follow spot-effect-using-html-CSS-and-jquery/](https://www.geeksforgeeks.org/how-to-create-followspot-effect-using-html-css-and-jquery/)

跟随点效果(聚光灯效果)是一种可以使用 jQuery 轻松实现的效果。这种效果在任何网站的开篇或正面横幅设计中都很受欢迎。
**方法:**方法是使用 jQuery 提供的 [mousemove()](https://www.geeksforgeeks.org/jquery-mousemove-with-examples/) 功能，在鼠标移动效果上使用圆形 CSS。
**HTML 代码:**HTML 代码用于设计身体的基本结构。在本节中，我们将使用一个< div >标签，该标签包装在一个<节>标签中。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content=
        "width=device-width, initial-scale=1.0" />

    <title>Split Effect</title>
</head>

<body>
    <section>
        <div class="geeks"></div>
    </section>
</body>

</html>
```

**CSS 代码:**CSS 属性用于设置图像的样式。

## 半铸钢ˌ钢性铸铁(Cast Semi-Steel)

```html
<style>
    body {
       margin: 0;
       padding: 0;
     }
     section {
       background: url(geeks.png);
       position: relative;
       width: 100%;
       height: 100vh;
       background-size: cover;
     }

     .geeks {
       position: absolute;
       width: 100%;
       height: 100%;
     }
</style>
```