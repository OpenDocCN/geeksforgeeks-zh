# 如何用 CSS 创建文字填充动画？

> 原文:[https://www . geesforgeks . org/how-create-text-fill-animation-using-CSS/](https://www.geeksforgeeks.org/how-to-create-text-fill-animation-using-css/)

悬停时的文本填充动画是现代网页设计理念的一种文本动画。在此动画中，文本填充了不同于原始文本的颜色-特定方向上的颜色，即从左到右、从右到左、从上到下或从下到上。
这类动画不仅限于文字。你可以使用同样的技术来填充任何部分或形状，就像填充玻璃或杯子可以很好地实现这个动画。

**方法:**方法是用不同颜色的图层覆盖文本，在开始时保持宽度为 0，在鼠标悬停时将宽度增加到 100%。

**HTML 代码:**在本节中，我们有一个带有数据-文本属性的“h1”元素，我们将使用它在原始文本上放置一个图层。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content=
        "width=device-width, initial-scale=1.0" />
    <title>Text Fill</title>
</head>

<body>
    <h1 data-text="Geeks">Geeks</h1>
</body>

</html>
```

**CSS 代码:**对于 CSS，请按照以下步骤操作。

*   **第一步:**应用一些基本的样式，如将文本对齐到中心和基本的背景颜色。
*   **第二步:**将内容设置为我们在“h1”标签中使用的属性。这将涵盖原文。
*   **第三步:**将宽度设置为 0，并设置不同于文本原始颜色的任何颜色。
*   **第 4 步:**现在鼠标悬停时将“宽度”设置为 100。

**注意:**鼠标悬停时，可以将“宽度”设置为任何其他值，以仅覆盖文本的特定部分。例如，将其设置为 50%，以便文本仅填充长度的一半。

```html
<style>
    h1 {
        margin: 0;
        padding: 0;
        position: absolute;
        top: 50%;
        left: 50%;
        font-size: 5em;
        color: #ccc;
    }

    h1::before {

        /* This will create the layer
           over original text*/
        content: attr(data-text);
        position: absolute;
        top: 0;
        left: 0;

        /* Setting different color than
           that of original text  */
        color: green;
        overflow: hidden;

        /* Setting width to 0*/
        width: 0%;
        transition: 1s;
    }

    h1:hover::before {

        /* Setting width to 100 on hover*/
        width: 100%;
    }
</style>
```

**完整代码:**是以上两段代码的组合。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content=
        "width=device-width, initial-scale=1.0" />
    <title>Text Fill</title>

    <style>
        h1 {
            margin: 0;
            padding: 0;
            position: absolute;
            top: 50%;
            left: 50%;
            font-size: 5em;
            color: #ccc;
        }

        h1::before {
            /* This will create the layer
               over original text*/
            content: attr(data-text);
            position: absolute;
            top: 0;
            left: 0;

            /* Setting different color than
               that of original text  */
            color: green;
            overflow: hidden;

            /* Setting width as 0*/
            width: 0%;
            transition: 1s;
        }

        h1:hover::before {

            /* Setting width to 100 on hover*/
            width: 100%;
        }
    </style>
</head>

<body>
    <h1 data-text="Geeks">Geeks</h1>
</body>

</html>
```

**输出:**
![](img/56e4ce8a12e53ea59a26c04b979bf42b.png)