# CSS |边框-内联-开始-颜色属性

> 原文:[https://www . geesforgeks . org/CSS-border-inline-start-color-property/](https://www.geeksforgeeks.org/css-border-inline-start-color-property/)

CSS 中的**边框内联开始颜色**属性用于在样式表中的一个位置定义单个逻辑内联结束边框属性值。此属性设置定义元素边框左侧的边框颜色。

**语法:**

```html
border-inline-start-color: border-color;
```

**属性值:**

*   **边框颜色:**该属性保存边框的颜色。

下面的例子说明了 CSS 中的**边框内联开始颜色属性**:

**例 1:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | border-inline-start-color Property</title>
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
            border-inline-start-color: yellow;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | border-inline-start-color Property</b>
        <br><br>
        <div class="one">A Computer Science Portal</div>
    </center>
</body>

</html>
```

**输出:**
![](img/388a1b55e6935e5cb5b5bae2b3f7695e.png)

**例 2:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | border-inline-start-color Property</title>
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
            border-inline-start-color: green;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | border-inline-start-color Property</b>
        <br><br>
        <div class="one">A Computer Science Portal</div>
    </center>
</body>

</html>
```

**输出:**
![](img/0acd63065a23858be214d01ae1e8e001.png)

**支持的浏览器:****边框内联开始颜色属性**支持的浏览器如下:

*   火狐浏览器
*   歌剧
*   边缘

**参考:**[https://developer . Mozilla . org/en-US/docs/Web/CSS/border-inline-start-color](https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-start-color)