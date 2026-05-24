# 如何在 CSS 中伪选择器前使用::放置背景图像？

> 原文:[https://www . geesforgeks . org/how-to-place-background-image-使用前伪选择器-in-css/](https://www.geeksforgeeks.org/how-to-place-background-image-using-before-pseudo-selectors-in-css/)

给定一个网页，任务是使用**:在**伪选择器之前将背景图像放置在网页上。

[**::在** **之前伪选择符** r](https://www.geeksforgeeks.org/css-before-selector/) 用于在所选项目的内容之前放置一些东西。

**语法:**

```html
.container::before{
    content: '';
    background: url(image file);
    position:absolute;
    top:0px;
    left:0px;
}
```

**方法:****:**之前伪选择器将背景图像放在所选元素之前，如果所选元素有与之关联的背景颜色，我们可以使用 **z-index** 属性使背景图像可见。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content=
        "width=device-width, initial-scale=1.0">

    <title>
        How to place the background image 
        using ::before pseudo selectors ?
    </title>

    <style>
        * {
            margin: 0px;
            padding: 0px;
        }

        body {
            text-align: center;
        }

        h1 {
            color: green;
        }

        .container {
            width: 100vw;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            color: black;
            font-weight: bold;
            font-size: 2rem;
        }

        .container::before {
            content: '';
            background: url('bg.png') 
                no-repeat center center/cover;
            position: absolute;
            opacity: 0.3;
            top: 0px;
            left: 0px;
            width: 100vw;
            height: 100vh;
            z-index: -1;
        }

        span {
            font-size: 2em;
        } 
    </style>
</head>

<body>
    <div class="container">
        GeeksforGeeks<br><br>
        How to place background image using
        ::before pseudo selectors ?
    </div>
</body>

</html>
```

**输出:**

![](img/640b904bfdbe70fb0591f66f08032fba.png)

**图片参考:**https://media . geesforgeks . org/WP-content/cdn-uploads/20200212230557/如何成为 2020 年网络开发者-完整指南. png