# CSS `border-end-start-radius` 属性

> 原文：[https://www.geeksforgeeks.org/css-border-end-start-radius-property/](https://www.geeksforgeeks.org/css-border-end-start-radius-property/)

CSS 中的 `border-end-start-radius` 属性用于指定块开始边界处的逻辑边界半径。它可以通过元素的 `writing-mode`、`direction` 和 `text-orientation` 进行调整。

**语法：**

```html
border-end-start-radius: length | percentage;
```

**默认值：** 其默认值为 `0`。

**属性值：**

*   `length`：该属性以特定单位保存边界半径长度。
*   `percentage`：此属性保存与父元素相比的百分比值。

以下示例说明了 CSS 中的 `border-end-start-radius` 属性：

## 例 1

```html
<!DOCTYPE html>
<html>
<head>
    <title>CSS | border-end-start-radius Property</title>
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
            border-end-start-radius: 10px;
        }
    </style>
</head>
<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | border-end-start-radius Property</b>
        <br><br>
        <div>
            <p class="one">A Computer Science Portal</p>
        </div>
    </center>
</body>
</html>
```

**输出：**

![](img/be5b0b022c4555171417d174eebc6d9e.png)

## 例 2

```html
<!DOCTYPE html>
<html>
<head>
    <title>CSS | border-end-start-radius Property</title>
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
            border-end-start-radius: 50%;
        }
    </style>
</head>
<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | border-end-start-radius Property</b>
        <br><br>
        <div>
            <p class="one">A Computer Science Portal</p>
        </div>
    </center>
</body>
</html>
```

**输出：**

![](img/5670f87422d7529d831fb6479194fb54.png)

**支持的浏览器：** `border-end-start-radius` 属性支持的浏览器如下：

*   Firefox