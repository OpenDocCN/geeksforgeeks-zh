# 使用 HTML 和 CSS 创建一个发光的文本阴影

> 原文:[https://www . geesforgeks . org/create-a-发光文本-阴影-使用-html-and-css/](https://www.geeksforgeeks.org/create-a-glowing-text-shadow-using-html-and-css/)

为了创建一个发光的文本阴影，我们将使用 HTML 来创建文本样式的结构和 CSS。在 CSS 的帮助下，我们可以给文本添加阴影。

**HTML 代码:**在本节中，我们将设计代码的基本结构。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" 
          content="width=device-width, 
                   initial-scale=1.0">
    <title>Glowing Text</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>Hello !</h1>
    <h1>GeeksforGeeks</h1>
</body>
</html>
```

**CSS 代码:**在本节中，我们将使用一些 CSS 属性来设计**发光文本阴影**。CSS 文本阴影属性对文本应用阴影。
文本阴影**CSS 属性为文本添加阴影。它接受一个逗号分隔的阴影列表，应用于文本及其任何装饰。每个阴影由元素的 X 和 Y 偏移、模糊半径和颜色的某种组合来描述。**

```html
body{
    background: black;
}

h1{
    margin-top: 150px;
    text-align: center;
    font-size: 60px;
    font-family: 'century gothic';
    color: #ffffcc;
    text-shadow: 0 0 5px #fff,
                 0 0 10px #fff, 
                 0 0 20px green, 
                 0 0 30px green, 
                 0 0 40px green, 
                 0 0 55px green, 
                 0 0 70px green;
}
```

**完整代码:**是以上两个代码段的组合。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" 
          content="width=device-width,
                   initial-scale=1.0">
    <title>Glowing Text</title>
    <style>
body{
    background: black;
}

h1{
    margin-top: 150px;
    text-align: center;
    font-size: 60px;
    font-family: 'century gothic';
    color: #ffffcc;
    text-shadow: 0 0 5px #fff,
                 0 0 10px #fff, 
                 0 0 20px green, 
                 0 0 30px green, 
                 0 0 40px green, 
                 0 0 55px green, 
                 0 0 70px green;
}
    </style>
</head>
<body>
    <h1>Hello !</h1>
    <h1>GeeksforGeeks</h1>
</body>
</html>
```

**输出:**
![](img/ec8ca0461b862c7ebeb139646331b62a.png)