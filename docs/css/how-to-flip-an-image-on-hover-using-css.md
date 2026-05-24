# 如何使用 CSS 在悬停时翻转图像？

> 原文:[https://www . geesforgeks . org/how-to-flip-a-image-on-hover-using-CSS/](https://www.geeksforgeeks.org/how-to-flip-an-image-on-hover-using-css/)

在本文中，您将学习当鼠标悬停在图像上时，如何水平和垂直翻转图像(添加镜像效果)。这可以通过对图像应用转换来完成，如下例所示:

**示例 1:** 该示例表示如何通过使用**变换:scaleX(-1)** 属性沿 X 轴变换来水平翻转图像。

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        img:hover{
            transform: scaleX(-1);
        }
    </style>
</head>

<body>
    <h2>GeeksforGeeks</h2>
    <img src="gfg.jpg" width="50%">
</body>

</html>
```

**输出:**

<video class="wp-video-shortcode" id="video-434023-1" width="665" height="375" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200612220316/6.1-final.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200612220316/6.1-final.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200612220316/6.1-final.mp4)</video>

**示例 2:** 该示例表示如何通过使用**变换:scaleY(-1)** 属性沿 Y 轴变换来垂直翻转图像。

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        img:hover{
            transform: scaleY(-1);
        }
    </style>
</head>

<body>
    <h2>GeeksforGeeks</h2>
    <img src="gfg.jpg" width="50%">
</body>

</html>
```

**输出:**

<video class="wp-video-shortcode" id="video-434023-2" width="665" height="375" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200612220621/6.2-final.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200612220621/6.2-final.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200612220621/6.2-final.mp4)</video>