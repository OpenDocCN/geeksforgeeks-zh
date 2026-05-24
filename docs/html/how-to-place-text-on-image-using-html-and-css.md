# 如何使用 HTML 和 CSS 在图像上放置文字？

> 原文:[https://www . geesforgeks . org/如何使用 html 和 css 在图像上放置文本/](https://www.geeksforgeeks.org/how-to-place-text-on-image-using-html-and-css/)

CSS **位置**属性用于设置文本在图像上的位置。这可以通过将图像和文本包含在一个 HTML“div”中来实现。然后将 div 的位置设为“相对”，将文本的位置设为“绝对”。绝对元素相对于其父元素(div)定位。这些元素的顶部、右侧、底部和左侧属性指定它们相对于父元素的位置。

**例 1:**

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        .gfg {
            margin: 3%;
            position: relative;
        }

        .first-txt {
            position: absolute;
            top: 17px;
            left: 50px;
        }

        .second-txt {
            position: absolute;
            bottom: 20px;
            left: 10px;
        }
    </style>
</head>

<body>
    <div class="gfg">
        <img src="gfg.png">
        <h3 class="first-txt">
            GeeksforGeeks
        </h3>

        <h3 class="second-txt">
            A computer science portal
        </h3>
    </div>
</body>

</html>
```

**输出:**
![](img/52223d48c87b704d89a500ecaee5f289.png)

**例 2:**

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        .gfg {
            margin: 3%;
            position: relative;
        }

        .first-txt {
            position: absolute;
            top: 17px;
            left: 20px;
        }

        .second-txt {
            position: absolute;
            top: 17px;
            left: 150px;
        }
    </style>
</head>

<body>
    <div class="gfg">
        <img src="gfg.png">
        <h3 class="first-txt">Left</h3>
        <h3 class="second-txt">Right</h3>
    </div>
</body>

</html>
```

**输出:**
![](img/dbcd04d722c9b902dec2cea5d29e35fe.png)

HTML 是网页的基础，通过构建网站和网络应用程序用于网页开发。您可以通过以下 [HTML 教程](https://www.geeksforgeeks.org/html-tutorials/)和 [HTML 示例](https://www.geeksforgeeks.org/html-examples/)从头开始学习 HTML。

CSS 是网页的基础，通过设计网站和网络应用程序用于网页开发。你可以通过以下 [CSS 教程](https://www.geeksforgeeks.org/css-tutorials/)和 [CSS 示例](https://www.geeksforgeeks.org/css-examples/)从头开始学习 CSS。