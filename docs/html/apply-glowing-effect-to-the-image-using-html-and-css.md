# 使用 HTML 和 CSS 对图像应用发光效果

> 原文:[https://www . geeksforgeeks . org/apply-fleed-effect-to-image-use-html-and-CSS/](https://www.geeksforgeeks.org/apply-glowing-effect-to-the-image-using-html-and-css/)

在浏览大多数网站时，你会看到一些特殊的效果，当你将光标放在不同的图片上时，可以看到这些效果。因此，在本文中，我们将实现相同的。我们可以用这样的图片作为我们网站的卡片。

在本文中，您将学习如何将发光效果应用于特定的图像，当您将光标放在图像上时，您将看到该效果。我们将用[**HTML****CSS**来实现。](https://www.geeksforgeeks.org/introduction-to-html-css-learn-to-design-your-first-website-in-just-1-week/)提供了一个示例视频，以便更清楚地了解您将在本文中开发什么。

![](img/508a6c6a638ee6fff64b162dbb92d347.png)

#### 逐步实施

#### 步骤 1:图像的 HTML 代码:

## 超文本标记语言

```html
<!-- Give a suitable heading using h1 tag-->
<h1 style="color: green; text-align: center;">
  GeeksForGeeks Glowling Card
</h1>
<div class="container">
  <!-- Set a image a background named gfg.jpg present in images folder -->
  <img class="GFG" src="images/gfg.jpg"
       alt="GeeksForGeeks" />
</div>
```

#### 步骤 2:使用 CSS 设置图像的样式:

现在，我们将应用一些 CSS 属性来装饰图像，并修复它在网页上的位置。关键是当用户将光标放在图像上时，使用 CSS 的**框影**属性使图像发光。下面是内部 CSS 代码给你的帮助。

## 超文本标记语言

```html
<style>

.GFG{

    width:200px ;
    height:250px;
    margin-left: 550px;
    border-radius: 10%;
}
.GFG:hover{
    color: #111; 
    background: greenyellow; 
    box-shadow: 0 0 100px greenyellow; 
}
</style>
```

#### 示例:

本示例使用**框阴影**属性对图像应用发光效果。你可以根据自己的需要改变背景的发光颜色。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>

    <style>
        .GFG {
            width: 200px;
            height: 250px;
            margin-left: 550px;
            border-radius: 10%;
        }

        .GFG:hover {
            color: #111;
            background: greenyellow;
            box-shadow: 0 0 100px greenyellow;
        }
    </style>
</head>

<body>

    <!-- Give a suitable heading using h1 tag-->
    <h1 style="color: green; text-align: center;">
        GeeksForGeeks Glowling Card
    </h1>
    <div class="container">
        <!-- Set a image a background named 
        gfg.jpg present in images folder -->
        <img class="GFG" src="images/gfg.jpg"
             alt="GeeksForGeeks" />
    </div>

</body>

</html>
```

这篇文章就到这里。下面是上面代码的输出视频。

### 输出:

![](img/508a6c6a638ee6fff64b162dbb92d347.png)