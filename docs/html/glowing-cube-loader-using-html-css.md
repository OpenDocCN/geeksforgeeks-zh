# 使用 HTML & CSS

的发光立方体加载器

> 原文:[https://www . geesforgeks . org/发光立方体-加载器-使用-html-css/](https://www.geeksforgeeks.org/glowing-cube-loader-using-html-css/)

**发光立方体加载器**可以使用 HTML 和 CSS 创建。我们将使用 HTML 来创建结构和一些 CSS 属性。

加载程序是操作系统中负责加载程序和库的部分。它是启动一个程序的过程中必不可少的阶段之一，因为它将程序放入内存并为执行做好准备。所以我们将使用 HTML 和 CSS 属性创建一个圆形加载器。

**HTML 代码:**在本节中，我们将设计代码的基本结构。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" 
          content="width=device-width, initial-scale=1.0">
    <title>Glowing cube loading</title>
    <link rel="stylesheet" href='style.css'>
</head>
<body>

   <h1>Loading GeeksforGeeks...</h1>
   <div class="loading"> 
        <span></span>
   </div>

</body>
</html>
```

**CSS 代码:**在本节中，我们将使用一些 CSS 属性来设计一个**发光立方体**。我们将使用指定动画代码的**@关键帧**。动画是通过从一组 CSS 样式逐渐改变到另一组样式来创建的。样式更改将以百分比或关键字“从”和“到”发生，这与 0%和 100%相同。我们可以多次更改 CSS 样式集。
用于@关键帧的语法是:**@关键帧 animationname {关键帧-选择器{ CSS-style；}}**

```html
body{
    background: black;
}
h1{ 
    margin-top: 300px;
    text-align: center;
    color: darkgreen;
}

.loading{

    width: 50px;
    height: 50px;
    margin: 100px auto;
    position: relative;
}

.loading span{
    display: block;
    position: absolute;
    bottom: 0;
    background: yellowgreen;
    width: 100%;
    height: 100%;
    border-radius: 10px;
    animation: loading 1.5s infinite ease-in-out;
}

@keyframes loading{
    0%{ 
        transform: rotate(0deg);
        background: yellow;
        box-shadow: 0 0 10px black, 
                    0 0 10px 5px green;
    }
    25%{
        transform: rotate(80deg);
        box-shadow: 0 0 10px #9966ff,
                    0 0 10px 5px black, 
                    0 0 10px 5px yellow;
    }
    100%{
        transform: rotate(0deg);
    }
}
```

**完整代码:**是以上两个代码段的组合，CSS 代码是使用**样式**标签在 HTML 代码内部添加的。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" 
          content="width=device-width,
                   initial-scale=1.0">
    <title>Glowing cube loading</title>
    <style>
body{
    background: black;
}
h1{ 
    margin-top: 300px;
    text-align: center;
    color: darkgreen;
}

.loading{

    width: 50px;
    height: 50px;
    margin: 100px auto;
    position: relative;
}

.loading span{
    display: block;
    position: absolute;
    bottom: 0;
    background: yellowgreen;
    width: 100%;
    height: 100%;
    border-radius: 10px;
    animation: loading 1.5s infinite ease-in-out;
}

@keyframes loading{
    0%{ 
        transform: rotate(0deg);
        background: yellow;
        box-shadow: 0 0 10px black,
                    0 0 10px 5px green;
    }
    25%{
        transform: rotate(80deg);
        box-shadow: 0 0 10px #9966ff,
                    0 0 10px 5px black,
                    0 0 10px 5px yellow;
    }
    100%{
        transform: rotate(0deg);
    }
}
     </style>
</head>
<body>

   <h1>Loading GeeksforGeeks...</h1>
   <div class="loading"> 
        <span></span>
   </div>

</body>
</html>
```

**输出:**
![](img/1993357b67408d3bd99cb6e4a3b0a055.png)