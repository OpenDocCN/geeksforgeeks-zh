# 如何在 CSS 中使用 flex 来缩小图像？

> 原文：[https://www.geeksforgeeks.org/how-to-use-flex-to-shrink-an-image-in-css/](https://www.geeksforgeeks.org/how-to-use-flex-to-shrink-an-image-in-css/)

您可以通过使用 CSS 中的 `flex-wrap` 属性来轻松地缩小图像，它指定折绕项目是强制成单行还是折绕成多行。`flex-wrap` 属性允许控制线条堆叠的方向。它用于指定单行或多行格式，以在 flex 容器内伸缩项目。

## 语法

```html
flex-wrap: wrap
```

## 注意

`wrap` 用于将伸缩项分割成多行。它使弹性项根据弹性项宽度换行到多行。

## 示例

为了缩小图像，必须使图像的宽度达到 100%，这样图像就占据了 100% 的 `<div>` 大小。

### HTML 代码

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        .container {
            display: -webkit-flex;
            -webkit-flex-wrap: wrap;
            display: flex;
            flex-wrap: wrap;
            background-color: grey;
        }

        img {
            width: 100%;
        }

        div {
            flex: 1;
            padding: 10px;
            margin: 10px;
        }
    </style>
</head>

<body>
    <div class="container">
        <div class="image">
            <img src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190710102234/download3.png" />
        </div>
        <div class="image">
            <img src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190710102234/download3.png" />
        </div>
        <div class="image">
            <img src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190710102234/download3.png" />
        </div>
    </div>
</body>

</html>
```

### 输出

![](img/964be9b3917353be6ea87e1e8aa68ebd.png)

伸缩包装属性