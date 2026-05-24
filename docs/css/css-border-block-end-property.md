# CSS |边框-块端属性

> 原文:[https://www . geesforgeks . org/CSS-border-block-end-property/](https://www.geeksforgeeks.org/css-border-block-end-property/)

CSS 中的**边框-块尾属性**用于在样式表的一个地方定义单个逻辑块尾边框属性值。此属性将边框放置在定义元素的底部。

**语法:**

```html
border-block-end: border-width|border-style|border-color;
```

**属性值:**

*   **边框宽度:**该属性值保存属性的宽度。
*   **边框样式:**该属性保存可以是虚线、实线等的边框样式。
*   **边框颜色:**该属性保存边框的颜色。

以下示例说明了 CSS 中的**边界块结束属性**:

**例 1:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | border-block-end Property</title>
    <style>
        h1 {
            color: green;
        }

        div {
            background-color: yellow;
            width: 220px;
            height: 40px;
        }
        .one {
            border-block-end: 5px solid yellow;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | border-block-end Property</b>
        <br><br>
        <div class="one">A Computer Science Portal</div>
    </center>
</body>

</html>
```

**输出:**
![](img/8b6656131641d947a2c97eb9ecf0fe96.png)

**例 2:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | border-block-end Property</title>
    <style>
        h1 {
            color: green;
        }

        div {
            background-color: yellow;
            width: 220px;
            height: 40px;
        }
        .one {
            border-block-end: medium dashed yellow;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | border-block-end Property</b>
        <br><br>
        <div class="one">A Computer Science Portal</div>
    </center>
</body>

</html>
```

**输出:**
![](img/b5ddafbfe2562301e936e78981e1edeb.png)

**支持的浏览器:****边框块端属性**支持的浏览器如下:

*   火狐浏览器
*   歌剧
*   边缘