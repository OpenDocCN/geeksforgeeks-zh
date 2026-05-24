# CSS |边框-内联-结束属性

> 原文:[https://www . geesforgeks . org/CSS-border-inline-end-property/](https://www.geeksforgeeks.org/css-border-inline-end-property/)

CSS 中的**边框内联结束**属性用于在样式表的单个位置定义单个逻辑内联结束边框属性值。此属性将边框放置在定义元素的底部。

**语法:**

```html
border-inline-end: border-width|border-style|border-color;
```

**属性值:**

*   **边框宽度:**该属性值保存边框内联结束属性的宽度。
*   **边框样式:**该属性保存可以是虚线、实线等的边框样式。
*   **边框颜色:**该属性保存边框的颜色。

以下示例说明了 CSS 中的**边框内联结束属性**:

**例 1:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | border-inline-end Property</title>
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
            border-inline-end: 5px solid yellow;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | border-inline-end Property</b>
        <br><br>
        <div class="one">A Computer Science Portal</div>
    </center>
</body>

</html>
```

**输出:**
![](img/f4b5772d9819c78ff37c72543e26633a.png)

**例 2:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | border-inline-end Property</title>
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
            border-inline-end: medium dashed yellow;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | border-inline-end Property</b>
        <br><br>
        <div class="one">A Computer Science Portal</div>
    </center>
</body>

</html>
```

**输出:**
![](img/e63a2a2f691c356c6f1b8adae01629c6.png)

**支持的浏览器:****边框内联端属性**支持的浏览器如下:

*   火狐浏览器
*   歌剧
*   边缘

**参考:**[https://developer . Mozilla . org/en-US/docs/Web/CSS/border-inline-end](https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-end)