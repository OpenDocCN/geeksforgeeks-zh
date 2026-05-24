# CSS |边框内联结束样式属性

> 原文:[https://www . geesforgeks . org/CSS-border-inline-end-style-property/](https://www.geeksforgeeks.org/css-border-inline-end-style-property/)

CSS 中的**边框内联结束样式**属性用于在样式表中的一个位置定义单个逻辑内联结束边框属性值。此属性设置定义元素边框底部的边框样式。

**语法:**

```html
border-inline-end-style: border-style;
```

**属性值:**

*   **边框样式:**该属性保存边框的样式。

以下示例说明了 CSS 中的**边框内联结束样式属性**:

**例 1:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | border-inline-end-style Property</title>
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
            border: 5px solid gray;
            border-inline-end-style: dotted;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | border-inline-end-style Property</b>
        <br><br>
        <div class="one">A Computer Science Portal</div>
    </center>
</body>

</html>
```

**输出:**
![](img/abb798bfe9caa3649e7393a4b04d02d5.png)

**例 2:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | border-inline-end-style Property</title>
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
            border: 5px solid black;
            border-inline-end-style: dashed;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | border-inline-end-style Property</b>
        <br><br>
        <div class="one">A Computer Science Portal</div>
    </center>
</body>

</html>
```

**输出:**
![](img/0404b11fef73ce13d386a1384aeb7056.png)

**支持的浏览器:****边框内联端样式属性**支持的浏览器如下:

*   火狐浏览器
*   歌剧
*   边缘

**参考:**[https://developer . Mozilla . org/en-US/docs/Web/CSS/border-inline-end-color](https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-end-color)