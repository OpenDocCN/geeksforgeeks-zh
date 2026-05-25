# html 5 中的网页滑台是什么？

> 原文：[https://www.geeksforgeeks.org/what-is-web-slide-desk-in-html5/](https://www.geeksforgeeks.org/what-is-web-slide-desk-in-html5/)

网络幻灯片是一个开源库，用于创建演示文稿、着陆、内容表格、长表单和具有 HTML 和 CSS 基本知识的投资组合。当我们有大量令人惊叹的第三方应用程序用于此目的时，您可能会怀疑网络幻灯片的必要性和重要性。我们可以很容易地推断出在互联网上展示我们的技能、想法和工作的不可或缺的重要性。如果我们能够使用一个紧凑、美观且易于使用的库来设计我们想要的展示会怎么样。易于设计，易于共享，没有兼容性问题。网络幻灯片为我们做到了这一点！

## 方法

我们可以从头开始创建网络幻灯片设计或定制演示。为了探索网络幻灯片，我们将从头开始制作几张幻灯片。首先，我们将分别设计两张幻灯片。然后我们将设计第三个，并结合所有这些来制作一个网络幻灯片。

让我们首先探索一下网络幻灯片的一些特性。

### 1. 背景

我们可以给幻灯片添加不同的背景：

*   在部分中添加 `bg-primary` 类，将 `#44d` 设置为背景。
*   在部分中添加 `bg-black-blue` 类，将 `#123` 设置为背景。
*   在剖面中添加 `bg-gradient-v` 类来设置垂直渐变背景。
*   在剖面中添加 `bg-gradient-r` 类设置径向渐变背景。
*   在剖面中添加 `bg-gradient-h` 类设置水平渐变背景。
*   在背景的 `span` 标记中，为不透明度低的透明背景添加 `dark` 类，为不透明度相对较高的透明背景添加 `light` 类。
*   您也可以通过在视频标签中指定类别 `background-video` 来使用视频作为背景。

通过在幻灯片部分指定适当的类别，可以使用更多的颜色作为背景。我们可以在屏幕上的不同位置放置背景，方法是使用 `span` 标签中的适当类作为背景。部分类有：

*   `background-center`
*   `background-center-top`
*   `background-center-bottom`
*   `background-left-side`
*   `background-right-top`

### 2. 包装

使用带有类 `wrap` 的 `div` 来布局内容，类可以正常工作。将内容放入此分区。

### 3. 对齐

您可以在不同的位置对齐您的内容。您可以将其左对齐、右对齐或居中对齐。此外，您可以将其放在幻灯片的顶部或底部。有些类是：

*   `content-left`
*   `content-right`
*   `content-center`
*   `slide-top`
*   `slide-bottom`
*   `align`
*   `align-right`
*   `size-30`
*   `size-50`

您也可以使用这些类的组合。

### 4. 动画

您可以在内容中使用不同的动画。只需将适当的类用于您想要制作动画的内容。类有：

### 5. 排版

你可以使用语义排版类来展示你的内容。所有这些类都使用 `Roboto` 字体，这就是为什么我们在标题标签中链接到它。`text-subtitle` 类将文本转换成大写字母。一些排版类如下：

*   `text-login`
*   `text-intro`
*   `text-shadow`
*   `text-data`
*   `text-context`
*   `text-columns`
*   `text-label`
*   `text-serif`
*   `text-pull-left`
*   `text-pull-right`

## 设计幻灯片的步骤

1.  [下载网络幻灯片。](https://webslides.tv/webslides-latest.zip)
2.  在根目录创建一个 HTML 文件 `yourFileName.html`。
3.  开始编码并将以下代码添加到 HTML 文件中。

### HTML

```html
<!DOCTYPE html>
<html>

<head>
    <meta charset="utf-8">
    <meta name="viewport" content=
        "width=device-width, initial-scale=1">

<!-- Linking to Roboto Google Fonts 
        used in webSlides -->
    <link rel="preconnect" href=
        "https://fonts.googleapis.com">
    <link rel="preconnect" href=
        "https://fonts.gstatic.com" crossorigin>
    <link href=
"https://fonts.googleapis.com/css2?family=Roboto:ital,
wght@0,100;0,300;0,400;0,500;0,700;0,900;1,100;1,300;1,
400;1,500;1,700;1,900&display=swap" rel="stylesheet">

<!--Linking to CSS WebSlides  -->
    <link rel="stylesheet" type='text/css'
        media='all' href="static/css/webslides.css">
</head>

<body></body>

</html>
```