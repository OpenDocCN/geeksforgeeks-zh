# 如何在 Bootstrap 4 中对齐图像？

> 原文:[https://www . geeksforgeeks . org/如何在引导中对齐图像-4/](https://www.geeksforgeeks.org/how-to-align-images-in-bootstrap-4/)

我们知道，在网站上添加图片会使网站更有吸引力，更有吸引力。有时，我们需要将图像向右或向左对齐。大多数时候，我们会在中心放置一个图像。使用传统的 CSS，我们必须编写一堆代码来完成这个特定的任务。Bootstrap 为图像提供了不同的类别，以使它们的外观更好，并使它们更具响应性。使图像具有响应性意味着它应该根据其父元素进行缩放。也就是说，图像的大小不应溢出其父元素，并将根据其父元素大小的变化而增长和收缩，而不会失去其纵横比。使用 Bootstrap 4，很容易应用预定义的 Bootstrap 类来对齐映像。在本文中，我们将学习在 Bootstrap 4 中对齐图像。

**语法:**

*   对于响应图像

```html
<img src="image_source" class="img-fluid" ...>
```

*   用于将图像向左对齐

```html
<img src="image_source" class="float-left" ...>
```

*   用于将图像向右对齐

```html
<img src="image_source" class="float-right" ...>
```

*   为了将图像对准中心

```html
<img src="image_source" class="mx-auto d-block" ...>
```

**进场:**

*   将图像放置在*[<>](https://www.geeksforgeeks.org/html-body-tag/)*标签内的所需行。
*   将图像元素包装在*中。* 班为向左对齐，*。向右浮动*向右对齐。
*   对于中心对齐，我们需要使用*。mx-auto* 和*。d-block* 类自举。
*   为了创建一个响应的图像，我们可以使用*。img-流体*类内的 [< img >标签](https://www.geeksforgeeks.org/html-img-tag/)。

我们将按照以下步骤对齐图像:

**步骤 1:** 在 HTML i [<头部>](https://www.geeksforgeeks.org/html-head-tag/) 部分包含 Bootstrap CSS 来加载样式表。

> <link rel="”stylesheet”" href="<br/">https://maxcdn . bootstracdn . com/bootstrap/4 . 0 . 0/CSS/bootstrap . min . CSS "
> 完整性= " sha 384-gn 5384 xqq 1 aowx a+058 r xpg 6 fy 4 iwvtnh 0 e 263 xmfcjlsawigfaw/dais 6 jxm "
> cross origin = " anonymous ">

添加引导 JavaScript 插件和依赖项。

**步骤 2:** 我们可以直接复制[官方引导文档](https://getbootstrap.com/docs/4.0/getting-started/introduction/)中给出的引导启动器模板。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <!-- Required meta tags -->
    <meta charset="utf-8" />
    <meta
      name="viewport"
      content="width=device-width, 
                     initial-scale=1, 
                     shrink-to-fit=no" />

    <!-- Bootstrap CSS -->
    <link
      rel="stylesheet"
      href=
"https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css"
      integrity=
"sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJlSAwiGgFAW/dAiS6JXm"
      crossorigin="anonymous"/>

    <title>Hello, world!</title>
  </head>
  <body>
    <h1>Hello, world!</h1>

    <!-- Optional JavaScript -->
    <!-- jQuery first, then Popper.js, then Bootstrap JS -->
    <script
      src=
"https://code.jquery.com/jquery-3.2.1.slim.min.js"
      integrity=
"sha384-KJ3o2DKtIkvYIK3UENzmM7KCkRr/rE9/Qpg6aAZGJwFDMVNA/GpGFF93hXpG5KkN"
      crossorigin="anonymous">
    </script>
    <script
      src=
"https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.12.9/umd/popper.min.js"
      integrity=
"sha384-ApNbgh9B+Y1QKtv3Rn7W3mgPxhU9K/ScQsAP7hUibX39j7fakFPskvXusvfa0b4Q"
      crossorigin="anonymous">
    </script>
    <script
      src=
"https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/js/bootstrap.min.js"
      integrity=
"sha384-JZR6Spejh4U02d8jOt6vLEHfe/JQGiRRSQQxSfFWpi1MquVdAyjUar5+76PVCmYl"
      crossorigin="anonymous">
    </script>
  </body>
</html>
```