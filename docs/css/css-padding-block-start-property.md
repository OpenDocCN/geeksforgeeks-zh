# CSS |填充块开始属性

> 原文:[https://www . geesforgeks . org/CSS-padding-block-start-property/](https://www.geeksforgeeks.org/css-padding-block-start-property/)

**填充块开始属性**用于定义元素的逻辑块开始填充。此属性有助于根据元素的书写模式、方向和文本方向放置填充。

**语法:**

```html
padding-block-start: length|percentage|auto|inherit|initial|unset;
```

**属性值:**

*   **长度:**设置 px、cm、pt 等定义的固定值。允许负值。它的默认值是 0px。
*   **百分比:**与长度相同，但大小是根据窗口大小的百分比设置的。
*   **自动:**当希望浏览器确定填充块开始大小时使用。
*   **初始值:**用于将填充块开始属性的值设置为默认值。
*   **inherit:** 当希望元素继承其父元素的 padding-block-start 属性作为自己的属性时使用。
*   **取消设置:**用于取消设置默认填充块开始。

下面的例子说明了 CSS 中的**填充块开始属性**:

**例 1:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | padding-block-start Property</title>
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
            padding-block-start: 40px;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | padding-block-start Property</b>
        <br><br>
        <div class="one">A Computer</div>
        <div class="two">Science Portal</div>
        <div class="three">For Geeks</div>
    </center>
</body>

</html>                    
```

**输出:**
![](img/b597ac516de70680ae56b68c05e9c7d5.png)

**例 2:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | padding-block-start Property</title>
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
            padding-block-start: 20px;
            writing-mode: vertical-lr;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | padding-block-start Property</b>
        <br><br>
        <div class="one">A Computer</div>
        <div class="two">Science Portal</div>
        <div class="three">For Geeks</div>
    </center>
</body>

</html>                                       
```

**输出:**
![](img/d1f33a2cdcfbd5f7986236855f0b6213.png)

**支持的浏览器:****填充块开始属性**支持的浏览器如下:

*   火狐浏览器
*   谷歌 Chrome
*   边缘
*   歌剧