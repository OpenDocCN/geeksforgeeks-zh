# CSS |边框-内联-开始属性

> 原文:[https://www . geesforgeks . org/CSS-border-inline-start-property/](https://www.geeksforgeeks.org/css-border-inline-start-property/)

CSS 中的**边框内联开始**属性用于在样式表中的一个位置定义单个逻辑内联结束边框属性值。此属性将边框放置在定义元素的左侧。

**语法:**

```html
border-inline-start: border-width| border-style| border-color;
```

**属性值:**

*   **边框宽度:**该属性值保存属性的宽度。
*   **边框样式:**该属性保存可以是虚线、实线等的边框样式。
*   **边框颜色:**该属性保存边框的颜色。

下面的例子说明了 CSS 中的**边框内联开始属性**:

**例 1:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | border-inline-start Property</title>
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
            border-inline-start: 5px solid yellow;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | border-inline-start Property</b>
        <br><br>
        <div class="one">A Computer Science Portal</div>
    </center>
</body>

</html>
```

**输出:**
![](img/50a5a7a32d0302592cf25cf04e1ff247.png)

**例 2:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | border-inline-start Property</title>
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
            border-inline-start: medium dashed yellow;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | border-inline-start Property</b>
        <br><br>
        <div class="one">A Computer Science Portal</div>
    </center>
</body>

</html>
```

**输出:**
![](img/7991d9aad6f83e9333811835ed9b451b.png)

**支持的浏览器:****边框内联启动属性**支持的浏览器如下:

*   火狐浏览器
*   歌剧
*   边缘

**参考:**[https://developer . Mozilla . org/en-US/docs/Web/CSS/border-inline-start](https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-start)