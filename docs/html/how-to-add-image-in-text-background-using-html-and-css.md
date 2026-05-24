# 如何使用 HTML 和 CSS 在文本背景中添加图像？

> 原文:[https://www . geesforgeks . org/如何使用 html 和 css 在文本背景中添加图像/](https://www.geeksforgeeks.org/how-to-add-image-in-text-background-using-html-and-css/)

在本文中，我们将使用 HTML 和 CSS 来设置文本背景中的图像。为了在文本背景中设置图像，使用了一些 CSS 属性。

**HTML 代码:** HTML 代码用于创建身体的基本结构。在下面的代码中，我们将使用段落标记来编写文本内容。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        How to Add Image in Text Background
        using HTML and CSS ?
    </title>
</head>

<body>
    <p>GeeksforGeeks</p>
</body>

</html>
```

**CSS 代码:**CSS 属性用于将图像设置为文本中的背景。background-image 属性用于将图像设置为背景。使用-webkit-text-fill-color 属性给文本一个透明的颜色，背景图像会通过文本显示出来，从而完成裁剪效果。

```html
<style>
    p {
        background-image: url(demo.jpg);
        background-repeat: repeat;
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        margin-top: 200px;
        font-size: 120px;
        text-align: center;
        font-weight: bold;
        text-transform: uppercase;
        font-family: 'Steelfish Rg', 'helvetica neue',
                    helvetica, arial, sans-serif;
        font-weight: 800;
        -webkit-font-smoothing: antialiased;
    }
</style>
```

**完整代码:**在本节中，我们将结合以上两个部分添加一个图像作为文本背景。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        How to Add Image in Text Background
        using HTML and CSS ?
    </title>

    <style>
        p {
            background-image: url(demo.jpg);
            background-repeat: repeat;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-top: 200px;
            font-size: 120px;
            text-align: center;
            font-weight: bold;
            text-transform: uppercase;
            font-family: 'Steelfish Rg', 'helvetica neue',
                     helvetica, arial, sans-serif;
            font-weight: 800;
            -webkit-font-smoothing: antialiased;
        }
    </style>
</head>

<body>
    <p>GeeksforGeeks</p>
</body>

</html>
```

**输出:**
![](img/727a7a506c2491f17c8ab0a8ceddc637.png)