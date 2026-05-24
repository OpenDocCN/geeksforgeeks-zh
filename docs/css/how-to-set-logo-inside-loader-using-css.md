# 如何使用 CSS 在装载机内部设置 logo？

> 原文:[https://www . geesforgeks . org/如何设置标志-内部加载器-使用-css/](https://www.geeksforgeeks.org/how-to-set-logo-inside-loader-using-css/)

在本文中，我们将学习如何使用 CSS 在加载器内部设置徽标。

加载器是提醒访问者/用户当前正在加载的页面的任何动画，您必须等待几秒钟才能完全加载。当任何网站花费太长时间来获取结果时，加载器通常是有帮助的，它不是给人一种网站没有响应的印象，而是给出一个简单的动画，表明网站仍然在获取结果，网页将在几秒钟内准备好。

要了解如何在 CSS 中添加加载器类，可以参考以下文章。

1.  [如何制作 CSS 加载器？](https://www.geeksforgeeks.org/how-to-make-css-loader/)
2.  [如何使用 HTML 和 CSS 创建动画加载环？](https://www.geeksforgeeks.org/how-to-create-animated-loader-ring-using-html-and-css/)

在装载机内添加公司标志为用户提供了一种个人风格，这是取代普通装载机的常见做法。

**进场:**

1.  我们将创建一个 HTML 文件，在其中我们将在主体内添加一个 HTML[*【div】*](https://www.geeksforgeeks.org/div-tag-html/)，以便在其中添加我们的加载器。
2.  我们创建了一个 CSS 文件来给我们的标志和加载程序动画效果。
3.  我们使用 [<链接>标签](https://www.geeksforgeeks.org/html-link-tag/)将 CSS 文件链接到我们的 HTML 文档，或者可以使用 [<样式>标签将 CSS 内容直接放置在 HTML 文件中。](https://www.geeksforgeeks.org/html-style-tag/)
4.  在 *div* 标签内，使用 [*< img >*](https://www.geeksforgeeks.org/html-img-tag/) 标签插入徽标，因此现在我们的徽标出现在我们的*加载器*类内。

**HTML:**

## index.html

```html
<!DOCTYPE html>
<html lang="en">

<head>

    <!-- We can use the style tag and 
        place the CSS content inside it -->
    <link rel="stylesheet" href="style.css">
</head>

<body>
    <div class="loader">
        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210610212340/gfglogo.png" />
    </div>
</body>

</html>
```

**CSS:** 在这一节中，我们定义了文档的样式，使其看起来有吸引力，所有的动画都添加在这里。

我们的 CSS 文件的创建将遵循以下步骤。

1.  添加加载程序类属性
    *   根据您想要制作的加载器的样式，添加合适的边框大小、颜色、半径、高度、宽度等。
    *   对于动画部分，我们将使用[@关键帧规则](https://www.geeksforgeeks.org/css-keyframes-rule/)，该规则允许动画以一定的时间间隔从当前样式逐渐变为新样式。
    *   然后最后我们将使用 [CSS Transform 属性](https://www.geeksforgeeks.org/css-transform-property/)将动画顺时针旋转 360 度。
2.  添加徽标类属性
    *   在 CSS 文件中，我们将我们的徽标称为”。因为我们在包含加载器类的 *div* 标签中声明了图像标签。
    *   我们定义了徽标的高度和宽度(最好小于或等于 loader 类)，以便它留在 loader 内部。
    *   最后，我们添加一个*关键帧*和动画属性，与加载器相同，但是我们不是顺时针旋转它，而是逆时针旋转它，以创建一个它实际上是固定的效果，而不是与加载器一起旋转。

**注意:**我们必须以相反的方向旋转徽标，因为我们已经在 loader 类内部定义了徽标，并且 loader 类中定义的所有属性也适用于徽标，因此为了消除旋转的影响，我们以逆时针方向旋转徽标，因此徽标看起来是静止的。

## style.css

```html
.loader {
    border: 16px solid #f3f3f3; /* Light grey */
    border-top: 16px solid #048023; /* Dark Green */
    border-radius: 50%;
    width: 120px;
    height: 120px;
    animation: spinloader 2s linear infinite;
}
.loader img{
    height : 120px;
    width : 120px;
    animation: spinlogo 2s linear infinite;
}
@keyframes spinloader {
    0% { transform: rotate(0deg); }
    100% { transform: rotate(360deg); }
}
@keyframes spinlogo {
    0% { transform: rotate(360deg); }
    100% { transform: rotate(0deg); }
}
```

**完整代码:**在本节中，我们将结合以上两段代码，即 HTML 和 CSS 代码。

## index.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <style type="text/css">
        .loader {
            border: 16px solid #f3f3f3;
            /* Light grey */
            border-top: 16px solid #048023;
            /* Dark Green */
            border-radius: 50%;
            width: 120px;
            height: 120px;
            animation: spinloader 2s linear infinite;
        }

        .loader img {
            height: 120px;
            width: 120px;
            animation: spinlogo 2s linear infinite;
        }

        @keyframes spinloader {
            0% {
                transform: rotate(0deg);
            }

            100% {
                transform: rotate(360deg);
            }
        }

        @keyframes spinlogo {
            0% {
                transform: rotate(360deg);
            }

            100% {
                transform: rotate(0deg);
            }
        }
    </style>
</head>

<body>
    <div class="loader">
        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210610212340/gfglogo.png" />
    </div>
</body>

</html>
```

**输出:**

![](img/86634c21cb0d0a719bd2545adce9ac71.png)