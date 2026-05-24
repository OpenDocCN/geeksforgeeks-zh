# CSS |边框-内联-起始宽度属性

> 原文:[https://www . geesforgeks . org/CSS-border-inline-start-width-property/](https://www.geeksforgeeks.org/css-border-inline-start-width-property/)

CSS 中的**边框内联开始宽度**属性用于在样式表中的一个位置定义单个逻辑内联结束边框属性值。此属性设置定义元素边框左侧的边框宽度。

**语法:**

```html
border-inline-start-width: border-width;
```

**属性值:**

*   **边框宽度:**该属性保存边框的宽度。

以下示例说明了 CSS 中的**边框内联起始宽度属性**:

**例 1:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | border-inline-start-width Property</title>
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
            border-inline-start-width: 8px;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | border-inline-start-width Property</b>
        <br><br>
        <div class="one">A Computer Science Portal</div>
    </center>
</body>

</html>
```

**输出:**
![](img/8a306fc3282651216c3065ce21f029a4.png)

**例 2:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | border-inline-start-width Property</title>
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
            border-inline-start-width: 2px;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | border-inline-start-width Property</b>
        <br><br>
        <div class="one">A Computer Science Portal</div>
    </center>
</body>

</html>
```

**输出:**
![](img/235416744d925568b14ae76ac05529cb.png)

**支持的浏览器:****边框内联起始宽度属性**支持的浏览器如下:

*   火狐浏览器
*   歌剧
*   边缘

**参考:**[https://developer . Mozilla . org/en-US/docs/Web/CSS/border-inline-start-width](https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-start-width)