# CSS |填充块属性

> 原文:[https://www.geeksforgeeks.org/css-padding-block-property/](https://www.geeksforgeeks.org/css-padding-block-property/)

CSS 中的**填充块属性**用于定义元素的逻辑块开始和结束填充。此属性有助于根据元素的书写模式、方向和文本方向放置填充。

**语法:**

```html
padding-block: length|percentage|auto|inherit|initial|unset;
```

**属性值:**

*   **长度:**设置 px、cm、pt 等定义的固定值。也允许负值。它的默认值是 0px。
*   **百分比:**它与长度相同，但它根据窗口大小的百分比设置填充块大小。
*   **自动:**当希望浏览器确定填充块大小时使用。
*   **初始值:**用于将填充块属性的值设置为默认值。
*   **inherit:** 当希望元素从其父元素继承填充块属性时使用。
*   **取消设置:**用于取消设置默认填充块属性值。

下面的例子说明了 CSS 中的**填充块属性**:

**例 1:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | padding-block Property</title>
    <style>
        h1 {
            color: green;
        }

        div {
            background-color: yellow;
            width: 110px;
            height: 80px;
        }
        .two {
            padding-block: 20px 40px;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | padding-block Property</b>
        <br><br>
        <div class="one">A Computer</div>
        <div class="two">Science Portal</div>
        <div class="three">For Geeks</div>
    </center>
</body>

</html>                    
```

**输出:**
![](img/73c58e26f38610fa3017556af3846140.png)

**例 2:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | padding-block Property</title>
    <style>
        h1 {
            color: green;
        }

        div {
            background-color: yellow;
            width: 110px;
            height: 80px;
        }
        .two {
            padding-block: 20px 40px;
            writing-mode: vertical-lr;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | padding-block Property</b>
        <br><br>
        <div class="one">A Computer</div>
        <div class="two">Science Portal</div>
        <div class="three">For Geeks</div>
    </center>
</body>

</html>                                       
```

**输出:**
![](img/6e6679c88f7fa3708dd8b53cd43b3db6.png)

**支持的浏览器:****填充块属性**支持的浏览器如下:

*   火狐浏览器
*   谷歌 Chrome
*   边缘
*   歌剧

**参考:**T2