# 如何在 HTML 中旋转图像？

> 原文:[https://www.geeksforgeeks.org/how-to-rotate-image-in-html/](https://www.geeksforgeeks.org/how-to-rotate-image-in-html/)

您可以使用 [CSS 变换属性轻松旋转 HTML 中的图像。](https://www.geeksforgeeks.org/css-transform-property/)该属性用于移动、旋转、缩放和执行元素的各种变换。

**方法:**可以使用[旋转()](https://www.geeksforgeeks.org/css-rotate-function/)函数，该函数被定义为一种变换，在不使元素变形的情况下，围绕 2D 平面上的固定点旋转元素。它采用一个定义旋转角度的参数。旋转角度由两部分组成，旋转值后跟旋转单位。单位可以用度数(度)、坡度(度)、弧度(弧度)和转角来定义。方法**旋转()**的值将顺时针旋转元素。

**注意:**要旋转 90 度，任何单位都可以使用其相应的值。90 度等于 100 个坡度或 0.25 圈。

**语法:**

```html
transform: rotate(90deg);
```

建议在 CSS 中添加以下代码，这样您的代码就可以兼容所有主要浏览器，因为使用其他浏览器的人会看到它颠倒过来。

**CSS 代码:**

```html
-webkit-transform:rotate(180deg); /* Chrome, Safari, Opera */
-moz-transform: rotate(180deg);
-ms-transform: rotate(180deg);
-o-transform: rotate(180deg);
transform: rotate(180deg);   /* Standard syntax */
```

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        .rotate_image {
            -webkit-transform: rotate(45deg);
            -moz-transform: rotate(45deg);
            -ms-transform: rotate(45deg);
            -o-transform: rotate(45deg);
            transform: rotate(45deg);
        }

        h1 {
            color: green;
        }
    </style>
</head>

<body>
    <h1>GeeksforGeeks</h1>

    <center>
        <img class="rotate_image"
            src=
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190710102234/download3.png"
            alt="GeeksforGeeks logo">
    </center>
</body>

</html>
```

**输出:**

*   **不使用变换:旋转()属性:**

![](img/49b4d0e122fde984e8027563b4300131.png)

*   **使用变换:旋转()属性:**

![](img/46697e4afb9bd6a57bbd42fdcb62e170.png)