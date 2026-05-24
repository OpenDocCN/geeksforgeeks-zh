# CSS `border-end-end-radius` 属性

> 原文: [https://www.geeksforgeeks.org/css-border-end-end-radius-property/](https://www.geeksforgeeks.org/css-border-end-end-radius-property/)

CSS 中的 `border-end-end-radius` 属性用于指定块结束边界处的逻辑边界半径。它可以通过元素的 `writing-mode`、`direction` 和 `text-orientation` 进行调整。

## 语法

```css
border-end-end-radius: length | percentage;
```

## 属性值

*   `length`: 该属性以特定单位保存边界半径长度。
*   `percentage`: 该属性保存相对于父元素的百分比值。

以下示例说明了 CSS 中的 `border-end-end-radius` 属性:

## 例 1

```html
<!DOCTYPE html>
<html>
<head>
    <title>CSS | border-end-end-radius Property</title>
    <style>
        h1 {
            color: green;
        }
        div {
            background-color: purple;
            width: 250px;
            height: 50px;
        }
        .one {
            background-color: yellow;
            border-end-end-radius: 10px;
        }
    </style>
</head>
<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | border-end-end-radius Property</b>
        <br><br>
        <div>
            <p class="one">A Computer Science Portal</p>
        </div>
    </center>
</body>
</html>
```

**输出:**
![](img/5aa220c0d8a0d39e923b855cf401678b.png)

## 例 2

```html
<!DOCTYPE html>
<html>
<head>
    <title>CSS | border-end-end-radius Property</title>
    <style>
        h1 {
            color: green;
        }
        div {
            background-color: purple;
            width: 250px;
            height: 50px;
        }
        .one {
            background-color: yellow;
            border-end-end-radius: 50%;
        }
    </style>
</head>
<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | border-end-end-radius Property</b>
        <br><br>
        <div>
            <p class="one">A Computer Science Portal</p>
        </div>
    </center>
</body>
</html>
```

**输出:**
![](img/71b25fd63ee2eb300f51764650b7412b.png)

## 支持的浏览器

`border-end-end-radius` 属性支持的浏览器如下:

*   火狐浏览器