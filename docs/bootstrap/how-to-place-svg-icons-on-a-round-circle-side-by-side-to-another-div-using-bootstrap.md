# 如何使用 Bootstrap 将一个圆上的 SVG 图标并排放置到另一个 div 上？

> 原文:[https://www . geesforgeks . org/how-to-place-SVG-icons-on-a-round-circle-并排到另一个 div-use-bootstrap/](https://www.geeksforgeeks.org/how-to-place-svg-icons-on-a-round-circle-side-by-side-to-another-div-using-bootstrap/)

引导图标是支持向量组，因此它们可以快速轻松地缩放，并且可以用 CSS 进行样式化。

**进场:**
我们可以放置 SVG 图标，给它们一个圆形的形状。这将使 SVG 图标看起来呈圆形。
这可以通过一个名为`"rounded-circle"`的引导类来实现

**语法:**

```html
<img class = "rounded-circle" src = "..." alt = "image">
```

**示例:**
让我们尝试将三个 SVG 图标放置在一个出现在同一条线上的圆上(根据需要并排)。
为了确保所有图标并排出现，我们必须在 CSS 中包含< img >标签的 **`float: left;`** 。

此外(可选)，我们还添加了引导类`"shadow-lg"`，在每个 SVG 图标下获得阴影，使其看起来不错。

**示例:**将此< img >标签放入< div >标签中，如下所示:

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8" />
        <meta name="viewport"
              content="width=device-width" />
        <title>JS Bin</title>
        <link rel="stylesheet"
              href=
"https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css" 
              integrity=
"sha384-JcKb8q3iqJ61gNV9KGb8thSsNjpSL0n8PARn9HuZOnIxN0hoP+VmmDGMN5t9UJ0Z" 
              crossorigin="anonymous" />
        <style>
            img {
                width: 100px;
                height: 100px;
                margin-top: 50px;
                float: left;
                margin-left: 10px;
            }
        </style>
    </head>
    <body>
        <div><img class="shadow-lg rounded-circle" 
                  src=
"https://img.icons8.com/emoji/2x/smiling-face.png" 
                  alt="image1" />
      </div>
        <div><img class="shadow-lg rounded-circle" 
                  src=
"https://img.icons8.com/emoji/2x/slightly-smiling-face.png" 
                  alt="image2" /></div>
        <div><img class="shadow-lg rounded-circle" 
                  src=
"https://img.icons8.com/emoji/2x/smiling-face-with-smiling-eyes.png" 
                  alt="image3" /></div>
    </body>
</html>
```

**输出:**
![](img/9b4ab177205e06d24cedc87e1ccf967f.png)

**参考文献:**

1.  [引导文件](https://getbootstrap.com/)
2.  微笑 SVG 图标
3.  [引导中的阴影](https://getbootstrap.com/docs/4.1/utilities/shadows/)