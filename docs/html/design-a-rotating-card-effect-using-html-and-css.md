# 使用 HTML 和 CSS 设计旋转卡效果

> 原文:[https://www . geesforgeks . org/design-a-rotating-card-effect-use-html-and-CSS/](https://www.geeksforgeeks.org/design-a-rotating-card-effect-using-html-and-css/)

旋转卡片是当你将鼠标悬停在卡片上时，卡片会在一定程度上旋转的效果。当你将鼠标悬停在卡片上时，卡片上会有信息、链接或图像。

在本文中，您将学习如何仅使用 [HTML 和 CSS](https://www.geeksforgeeks.org/introduction-to-html-css-learn-to-design-your-first-website-in-just-1-week/) 在您的网站上制作旋转卡片。

**分步实施:**

**第一步:卡片的 HTML 文件**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <meta name="viewport" content=
        "width=device-width, initial-scale=1">
</head>

<body>

    <!-- Give a proper heading-->
    <h1 style="color: green; text-align: center;">
        GeeksForGeeks Rotating Card
    </h1>

    <div="container">

        <!-- create a class to build the 
            structure of card using div-->
        <div class="card GFG"></div>
    </div>
</body>

</html>
```

**第二步:使用 CSS 装饰卡片正面:**我们已经在 HTML 部分构建了卡片第一面的结构。现在需要设计不同 CSS 属性的卡片，关键是利用 CSS 的*变换*属性，将卡片旋转 45 度，即*变换:旋转(45 度)* **。**所以，现在在*头* 标签里面添加下面写好的 CSS 代码。

```html
.card {
    position: absolute;
    width: 200px;
    height: 200px;
    display: inline-block;
    border-radius: 10px;
    padding: 15px 25px;
    box-sizing: border-box;
    cursor: pointer;
    margin: 10px 15px;
    transition: transform 0.5s;
    background-position: right;
    background-size: cover;
    transform: rotate(45deg);
}

.GFG {
    margin-top: 170px;
    margin-left: 600px;
    background-image: url(gfg.jpg);
}

.card:hover {
    transform: translateY(-10px);
}
```

**注意:**你可以根据*变换尽可能旋转你的卡片:旋转(45 度)*并且*背景图像*在**图像**文件夹中，我们将使用 **url()** 访问该图像，并且该 **url()** 将采用保存图像的地址。

**示例:**给出完整的 HTML 代码作为示例，供您参考。本示例使用*变换:旋转(45 度)*属性来旋转卡片。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <meta name="viewport" content=
        "width=device-width, initial-scale=1">

    <!-- CSS code -->
    <style>
        .card {
            position: absolute;
            width: 200px;
            height: 200px;
            display: inline-block;
            border-radius: 10px;
            padding: 15px 25px;
            box-sizing: border-box;
            cursor: pointer;
            margin: 10px 15px;
            transition: transform 0.5s;
            background-position: right;
            background-size: cover;
            transform: rotate(45deg);
        }

        .GFG {
            margin-top: 170px;
            margin-left: 600px;
            background-image: url(gfg.jpg);
        }

        .card:hover {
            transform: translateY(-10px);
        }
    </style>
</head>

<body>

    <!-- Give a proper heading-->
    <h1 style="color: green; text-align: center;">
        GeeksForGeeks Rotating Card
    </h1>

    <div="container">

        <!-- Create a class to build the 
            structure of card using div-->
        <div class="card GFG"></div>
    </div>
</body>

</html>
```

**输出:**

<video class="wp-video-shortcode" id="video-555468-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210206203622/gfgout2-2021-02-06_20.34.26.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210206203622/gfgout2-2021-02-06_20.34.26.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210206203622/gfgout2-2021-02-06_20.34.26.mp4)</video>