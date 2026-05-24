# 如何使用 HTML 和 CSS 将一个 logo 图像对齐导航栏中心？

> 原文:[https://www . geesforgeks . org/如何使用 html 和 css 将徽标图像对齐到导航栏中心/](https://www.geeksforgeeks.org/how-to-align-a-logo-image-to-center-of-navigation-bar-using-html-and-css/)

**问题陈述:**您一定看到了，当对导航栏中的图像标签应用*边距:自动*属性时，导航栏中的徽标图像不会居中。

**方法:**由于 CSS 中的图像标签是一个内联元素，所以图像标签只会占用它所需要的空间。因此，为了解决这个问题，我们将图像标签的*显示*属性指定为“块”，然后为其指定适当的宽度和高度。将*边距*指定为“自动”。您将看到徽标图像现在位于导航栏的中央。

**HTML 代码:**下面演示了上述方法的代码。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content=
        "width=device-width, initial-scale=1.0">

    <style>
        #navbar {
            width: 100vw;
            height: 40px;
            border: 3px solid white;
            border-radius: 15px;
            background-color: green;
        }

        #navbar img {
            display: block;
            width: 40px;
            height: 40px;
            margin: auto;

        }
    </style>
</head>

<body>
    <nav id="navbar">
        <img src="5.jpeg" alt="Logo image">
    </nav>
</body>

</html>
```

**输出:**

![](img/233b6f5eb7667423ece689b972ef3de1.png)