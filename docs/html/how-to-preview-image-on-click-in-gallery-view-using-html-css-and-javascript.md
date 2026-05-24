# 如何使用 HTML、CSS 和 JavaScript 在图库视图中点击预览图像？

> 原文:[https://www . geesforgeks . org/how-preview-image-on-click-in-gallery-view-use-html-CSS-and-JavaScript/](https://www.geeksforgeeks.org/how-to-preview-image-on-click-in-gallery-view-using-html-css-and-javascript/)

在本文中，我们看到了如何使用 HTML、CSS 和一些 JavaScript 轻松创建具有预览功能的图像库。

**HTML:**

*   用类容器创建 div。
*   在第一个 div 中再创建两个 div，一个用于主视图，另一个用于侧视图，类有 main_view 和 side_view。
*   在主视图中插入一个带有 id main 的图像标签。
*   在侧视图中，插入图库中所有其他具有功能变化的图像，并将图像的 src 传递给功能。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body>
      <!-- Container for our gallery -->
    <div class="container">
        <!-- Main view of our gallery -->
        <div class="main_view">
            <img src="one.jpg" id="main" alt="IMAGE">
        </div>

        <!-- All images with side view -->
        <div class="side_view">
            <img src="one.jpg" onclick="change(this.src)">
            <img src="two.jpg" onclick="change(this.src)">
            <img src="three.jpg" onclick="change(this.src)">
            <img src="four.jpg" onclick="change(this.src)">
        </div>
    </div>
</body>

</html>
```

CSS:

*   给容器指定宽度和边距。
*   给出主视图的高度和宽度。
*   在 main_view 中设置图像的尺寸。
*   使用 flex 设置 side_view 以适当的尺寸显示所有图像。

## 超文本标记语言

```html
<style type="text/css">
    /*Setting Basic Dimensions to give
    gallery view */
    .container{
        margin: 0 auto;
        width: 90%;
    }
    .main_view{
        width: 80%;
        height: 25rem;
    }
    .main_view img{
        width: 100%;
        height: 100%;
        object-fit: cover;
    }
    .side_view{
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
    }
    .side_view img{
        width: 9rem;
        height: 7rem;
        object-fit: cover;
        cursor: pointer;
        margin:0.5rem;
    }
</style>
```

**JavaScript:** 使用 change 函数，我们将把 main_view 的 src 替换为被点击图像的来源。

## java 描述语言

```html
const change = src => {
    document.getElementById('main').src = src
}
```

**最终代码:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <style type="text/css">
        /*Setting Basic Dimensions to give
        gallery view */
        .container{
            margin: 0 auto;
            width: 90%;
        }
        .main_view{
            width: 80%;
            height: 25rem;
        }
        .main_view img{
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        .side_view{
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
        }
        .side_view img{
            width: 9rem;
            height: 7rem;
            object-fit: cover;
            cursor: pointer;
            margin:0.5rem;
        }
    </style>
</head>

<body>
    <!-- Container for our gallery -->
    <div class="container">

        <!-- Main view of our gallery -->
        <div class="main_view">
            <img src="one.jpg" id="main" alt="IMAGE">
        </div>

        <!-- All images with side view -->
        <div class="side_view">
            <img src="one.jpg" onclick="change(this.src)">
            <img src="two.jpg" onclick="change(this.src)">
            <img src="three.jpg" onclick="change(this.src)">
            <img src="four.jpg" onclick="change(this.src)">
        </div>
    </div>

    <script type="text/javascript">
        const change = src => {
            document.getElementById('main').src = src
        }
    </script>
</body>

</html>
```

**输出:**

![](img/dde9b36dc673f2614bd2a85f371541ee.png)