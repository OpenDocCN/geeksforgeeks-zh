# 如何在 CSS 中融合元素？

> 原文：[https://www.geeksforgeeks.org/how-to-blend-elements-in-css/](https://www.geeksforgeeks.org/how-to-blend-elements-in-css/)

混合模式用于确定两个层（颜色和/或图像）如何相互混合。在本文中，我们将看到如何使用 CSS 混合元素。

**方法：** 在 CSS 中，有两个属性允许我们将颜色和/或图像混合在一起：

*   [`mix-blend-mode`](https://www.geeksforgeeks.org/css-mix-blend-mode-property/)
*   [`background-blend-mode`](https://www.geeksforgeeks.org/css-background-blend-mode-property/)

## 1. 使用 `mix-blend-mode` 属性

`mix-blend-mode` 属性用于混合元素及其后面的元素。

**语法：**

> `mix-blend-mode: normal | multiply | screen | color-dodge | difference | darken | lighten | saturation | luminosity | overlay | hard-light | soft-light | exclusion | hue | color-burn | color;`

**示例：** 以下示例演示了 HTML [`div`](https://www.geeksforgeeks.org/div-tag-html/) 元素与 CSS 部分中提到的一个背景图像的混合。

### HTML

```html
<!DOCTYPE html>
<html>

<head>

<style>
        .divName1 {
            background-image: url(
"https://media.geeksforgeeks.org/wp-content/uploads/20210622101607/image1.png");
            text-align: center;
            background-size: 1400px 360px;
        }

.divName1 h3 {
            margin: 0;
            font-size: 4.8rem;
            text-transform: uppercase;
            line-height: 1.9;
            color: green;
            mix-blend-mode: multiply;
        }
    </style>

</head>

<body>
    <center>
        <div class="divName1">
            <h3>Geeks for Geeks</h3>
        </div>
    </center>
</body>

</html>
```

**输出：**

![](img/a4d5f20302e06c5a35718fa134290956.png)

代码的输出

## 2. 使用 `background-blend-mode` 属性

`background-blend-mode` 属性用于混合背景图像及其背景颜色元素。

**语法：**

> `background-blend-mode: normal | multiply | screen | color-dodge | difference | darken | lighten | saturation | luminosity | overlay | hard-light | soft-light | exclusion | hue | color-burn | color;`

**示例：**

### HTML

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        #divName1 {
            width: 400px;
            height: 400px;
            background-repeat: no-repeat;
            background-image: 
url("https://media.geeksforgeeks.org/wp-content/uploads/20210622101952/circle.png"),
url("https://media.geeksforgeeks.org/wp-content/uploads/20210622102302/dog1.png");
            background-blend-mode: multiply;
        }
    </style>
</head>

<body>
    <center>
        <h2> background-blend-mode</h2>
        <div id="divName1"></div>
    </center>
</body>

</html>
```

**输出：**

![](img/dbd9fe0ab27a3ce663f00dd17c7bdc6d.png)

代码的输出