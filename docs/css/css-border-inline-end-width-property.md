# CSS |边框-内联-端宽属性

> 原文:[https://www . geesforgeks . org/CSS-border-inline-end-width-property/](https://www.geeksforgeeks.org/css-border-inline-end-width-property/)

CSS 中的**边框内联结束宽度**属性用于在样式表中的一个位置定义单个逻辑内联结束边框属性值。此属性设置定义元素边框底部的边框宽度。

**语法:**

```html
border-inline-end-width: border-width;
```

**属性值:**

*   **边框宽度:**该属性保存边框的宽度。

下面的例子说明了 CSS 中的**边框内联结束宽度属性**:

**例 1:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | border-inline-end-width Property</title>
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
            border-inline-end-width: 8px;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | border-inline-end-width Property</b>
        <br><br>
        <div class="one">A Computer Science Portal</div>
    </center>
</body>

</html>
```

**输出:**
![](img/89788799b8540e85151293d42c788adc.png)

**例 2:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | border-inline-end-width Property</title>
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
            border-inline-end-width: 2px;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | border-inline-end-width Property</b>
        <br><br>
        <div class="one">A Computer Science Portal</div>
    </center>
</body>

</html>
```

**输出:**
![](img/bf7e9d2893babd3efed619afbcdaab8f.png)

**参考:**[https://developer . Mozilla . org/en-US/docs/Web/CSS/border-inline-end-width](https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-end-width)

**支持的浏览器:****边框内联端宽属性**支持的浏览器如下:

*   火狐浏览器
*   歌剧
*   边缘