# 如何创建包含多个固定大小图像的 div？

> 原文: [https://www.geeksforgeeks.org/how-to-create-a-div-that-contains-multiple-fixed-size-images/](https://www.geeksforgeeks.org/how-to-create-a-div-that-contains-multiple-fixed-size-images/)

## 什么是 `<div>` 标签？

一个 `<div>` 标签可以定义为两个 HTML 代码块的分割线。它被用作 HTML 元素的容器，然后可以用 CSS 或 Javascript 进行样式化。`class` 或 `id` 属性可用于轻松设置 `<div>` 标签中元素的样式。

请阅读本文了解更多关于 `<div>` 标签: [https://www.geeksforgeeks.org/div-tag-html/](https://www.geeksforgeeks.org/div-tag-html/)

## 如何使用 `<div>` 标签的示例:

```html
<!DOCTYPE html>
<html>
<head>
    <style>
        .firstDiv {
            border: 5px outset black;
            background-color: green;
            text-align: center;
        }
    </style>
</head>
<body>
    <div class="firstDiv">
        <h2>Hello Geek!</h2>
        <p>How was your day like?</p>
    </div>
</body>
</html>
```

**输出:**
![](img/11ce1042efd1576037ce91a6d7ebc975.png)

## 创建一个包含多个固定大小图像的 `<div>`

**进场:**

*   首先，创建上例中提到的 `<div>` 标签，并将多个图像插入到一个公共的 `<div>` 标签中，这样所有的图像都有一个单独的 `<div>` 标签和一个类名。
*   以下示例显示了如何制作包含多个固定大小图像的 `<div>` 标签:

```html
<!DOCTYPE html>
<html>
<head>
    <style>
        .images {
            display: flex;
            flex-wrap: wrap;
            margin: 0 50px;
            padding: 30px;
        }
        .photo {
            max-width: 31.333%;
            padding: 0 10px;
            height: 240px;
        }
        .photo img {
            width: 100%;
            height: 100%;
        }
    </style>
</head>
<body>
    <div class="images">
        <div class="photo">
            <img src="tom1.jpg" alt="photo" />
        </div>
        <div class="photo">
            <img src="tom2.jpg" alt="photo" />
        </div>
        <div class="photo">
            <img src="tom3.jpg" alt="photo" />
        </div>
    </div>
</body>
</html>
```

**说明:** 在上面的代码中，我们创建了一个 `class="images"` 的主容器 `<div>` 类，用于存储所有的图像，每个图像都有自己的 `class="photo"` 容器 `<div>` 类，以后可以用来给图像添加特殊的 CSS 属性。

### 输出:

![](img/a64e8d0501fb2093cd11f9719fd10e8e.png)

显示的图像包含在 `class="images"` 的 `<div>` 标签中。