# 如何使用 CSS 给背景图像添加滤镜？

> 原文：`https://www.geeksforgeeks.org/how-to-add-filter-to-the-background-image-using-css/`

本文的目的是学习如何使用 CSS 向图像添加滤镜。CSS `滤镜`属性用于设置元素的视觉效果。此属性主要用于图像内容。

**语法：**

> `滤镜: 无 | blur() | brightness() | contrast() | drop-shadow() | grayscale() | hue-rotate() | invert() | opacity() | saturate() | sepia() | url()；`

**示例：**

## 示例一

```html
<!DOCTYPE html>
<html>
<head>
    <style>
        body {
            background-image: url("https://media.geeksforgeeks.org/wp-content/uploads/rk.png");
            filter: brightness(90%);
            filter: grayscale(70%);
        }
    </style>
</head>
<body>
    <center>
        <h2>GeeksForGeeks</h2>
        <h2>How to add a filter to a background image using CSS?</h2>
    </center>
</body>
</html>
```

**输出：**

![](img/89722e1bb4c69acd0c6e8a86526e4025.png)

## 示例二

```html
<!DOCTYPE html>
<html>
<head>
    <style>
        .darkened-image {
            filter: brightness(50%);
            background-image: url("https://media.geeksforgeeks.org/wp-content/cdn-uploads/20191121162913/s11.png");
            height: 94px;
            width: 120px;
        }
    </style>
</head>
<body>
    <h1 style="color: green">GeeksForGeeks</h1>
    <p>The image below is the normal image</p>
    <img src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/20191121162913/s11.png">
    <p>The image below is the darkened image:</p>
    <div class="darkened-image"></div>
</body>
</html>
```

**输出：**

![](img/19133485f8403cded45a23a9a71604bf.png)

**支持的浏览器：**

*   `谷歌 Chrome`
*   `微软 Edge`
*   `火狐浏览器`
*   `Opera`
*   `Safari`