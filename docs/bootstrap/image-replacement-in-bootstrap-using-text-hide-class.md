# 使用文本隐藏类在引导中替换图像

> 原文:[https://www . geesforgeks . org/image-replacement-in-bootstrap-use-text-hide-class/](https://www.geeksforgeeks.org/image-replacement-in-bootstrap-using-text-hide-class/)

Bootstrap 允许我们用背景图像替换任何文本元素的文本，比如段落元素、标题元素等。使用**。text-hide** 类，我们可以用背景图像替换一个元素的内容。

**语法:**

```html
<element class = "text-hide" 
         style = "background-image: url('Specify URL of image here');">
</element>

```

在上面的语法中，**文本隐藏**类用于首先隐藏元素的文本，并使用 [CSS 背景图像属性](https://www.geeksforgeeks.org/css-background-image-property/)将背景图像添加到元素中。

**示例:**

```html
<html>
<head>
    <!-- Link Bootstrap CSS and JS -->
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css">
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js"></script>
    <link href="https://fonts.googleapis.com/css?family=Lobster" rel="stylesheet">
</head>
<body>
    <h1 class="text-hide" 
        style="background-image: url('https://media.geeksforgeeks.org/wp-content/cdn-uploads/GeeksforGeeksLogoHeader.png'); 
               background-repeat: no-repeat; 
               width: 500px; height: 500px; ">
        GeeksforGeeks
    </h1>
</body>
</html>
```

**输出:**
![](img/19198a2eec40fcc60cf3e03469a6e9ca.png)

**注**:这个类也有助于提高网站的 SEO，因为使用这个类我们可以使用标题标签给网站添加图片，使用标题标签被发现对网页的 SEO 有好处。