# CSS |填充块结束属性

> 原文:[https://www . geesforgeks . org/CSS-padding-block-end-property/](https://www.geeksforgeeks.org/css-padding-block-end-property/)

CSS 中的**填充块结束属性**用于定义元素的逻辑块结束填充。此属性有助于根据元素的书写模式、方向和文本方向放置填充。

**语法:**

```html
padding-block-end: length|percentage|auto|inherit|initial|unset;
```

**属性值:**

*   **长度:**设置 px、em、pt 中定义的固定值。允许负值。它的默认值是 0px。
*   **百分比:**用于根据元素宽度的百分比设置填充块结束值。
*   **自动:**当希望浏览器确定块大小时使用。
*   **初始值:**用于将块大小属性的值设置为默认值。
*   **inherit:** 当希望元素继承其父元素的块大小属性作为自己的属性时使用。
*   **取消设置:**用于取消设置默认块大小。

以下示例说明了 CSS 中的**填充块结束属性**:
**示例 1:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | padding-block-end Property</title>
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
            padding-block-end: 40px;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | padding-block-end Property</b>
        <br><br>
        <div class="one">A Computer</div>
        <div class="two">Science Portal</div>
        <div class="three">For Geeks</div>

    </center>
</body>

</html>                    
```

**输出:**
![](img/000249e8894874dbf66765008515a412.png)

**例 2:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | padding-block-end Property</title>
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
            padding-block-end: 20px;
            writing-mode: vertical-lr;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | padding-block-end Property</b>
        <br><br>
        <div class="one">A Computer</div>
        <div class="two">Science Portal</div>
        <div class="three">For Geeks</div>

    </center>
</body>

</html>                                       
```

**输出:**
![](img/ffc20f0e23d7bd31240bfec1b59b3a75.png)

**支持的浏览器:****填充块结束属性**支持的浏览器如下:

*   火狐浏览器
*   谷歌 Chrome
*   边缘
*   歌剧

**参考:**[https://developer . Mozilla . org/en-US/docs/Web/CSS/padding-block-end](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-block-end)