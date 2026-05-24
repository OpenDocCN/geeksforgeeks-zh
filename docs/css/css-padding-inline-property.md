# CSS |填充-内嵌属性

> 原文:[https://www.geeksforgeeks.org/css-padding-inline-property/](https://www.geeksforgeeks.org/css-padding-inline-property/)

CSS 中的**填充内联属性**用于定义元素的逻辑内联开始和结束填充。此属性有助于根据元素的书写模式、方向和文本方向放置填充。

**语法:**

```html
padding-inline: length|percentage|auto|inherit|initial|unset;
```

**属性值:**

*   **长度:**设置 px、cm、pt 等定义的固定值。允许负值。它的默认值是 0px。
*   **百分比:**这与长度相同，长度是根据窗口大小的百分比设置的。
*   **自动:**由浏览器决定。
*   **初始值:**用于将 padding-inline 属性的值设置为默认值。
*   **inherit:** 当希望元素继承其父元素的 padding-inline 属性作为自己的属性时使用。
*   **取消设置:**用于取消设置默认内联填充。

下面的例子说明了 CSS 中的**填充内联属性**:

**例 1:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | padding-inline Property</title>
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
            padding-inline: 20px 40px;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | padding-inline Property</b>
        <br><br>
        <div class="one">A Computer</div>
        <div class="two">Science Portal</div>
        <div class="three">For Geeks</div>
    </center>
</body>

</html>                    
```

**输出:**
![](img/f93499f81bacd15872b8e776f32f581f.png)

**例 2:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | padding-inline Property</title>
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
            padding-inline: 20px 40px;
            writing-mode: vertical-lr;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | padding-inline Property</b>
        <br><br>
        <div class="one">A Computer</div>
        <div class="two">Science Portal</div>
        <div class="three">For Geeks</div>
    </center>
</body>

</html>                                       
```

**输出:**
![](img/10f9f48a02ec20aed1c04f3522b2fed3.png)

**参考:**[https://developer . Mozilla . org/en-US/docs/Web/CSS/padding-inline](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-inline)

**支持的浏览器:****填充内联属性**支持的浏览器如下:

*   火狐浏览器
*   谷歌 Chrome
*   边缘
*   歌剧