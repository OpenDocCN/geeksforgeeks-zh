# CSS | 边框内联颜色属性

> 原文：[https://www.geeksforgeeks.org/css-border-inline-color-property/](https://www.geeksforgeeks.org/css-border-inline-color-property/)

CSS 中的`border-inline-color`属性用于在样式表的单个位置设置单个逻辑内联边框颜色属性值。它设置定义边框元素的顶部和底部的边框颜色。

**语法：**

```html
border-inline-color: color;
```

**属性值：**

*   `color`：该属性保存边框的颜色。

以下示例说明了 CSS 中的`border-inline-color`属性：

**例 1：**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | border-inline-color Property</title>
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
            border: 5px solid cyan;
            border-inline-color: yellow;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | border-inline-color Property</b>
        <br><br>
        <div class="one">A Computer Science Portal</div>
    </center>
</body>

</html>
```

**输出：**
![](img/6d646f18574291e507c0ad04325f82e6.png)

**例 2：**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | border-inline-color Property</title>
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
            border: 5px dotted cyan;
            border-inline-color: yellow;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | border-inline-color Property</b>
        <br><br>
        <div class="one">A Computer Science Portal</div>
    </center>
</body>

</html>
```

**输出：**
![](img/1d093d0a45d79068ddea8fbef9bed3be.png)

**参考：**[https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-color](https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-color)

**支持的浏览器：**`border-inline-color`属性支持的浏览器如下：

*   火狐浏览器
*   歌剧
*   边缘