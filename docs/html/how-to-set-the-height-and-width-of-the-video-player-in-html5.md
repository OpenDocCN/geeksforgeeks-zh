# 如何在 HTML5 中设置视频播放器的高度和宽度？

> 原文:[https://www . geesforgeks . org/如何设置 html5 中视频播放器的高度和宽度/](https://www.geeksforgeeks.org/how-to-set-the-height-and-width-of-the-video-player-in-html5/)

在本文中，我们将学习在 HTML5 中设置视频播放器的*宽度*和*高度*。

以下是两种情况

*   视频的宽度和高度是固定的。
*   让视频符合您的屏幕宽度。

**方式:**视频标签的 HTML5 [宽度](https://www.geeksforgeeks.org/html-video-width-attribute/)和[高度](https://www.geeksforgeeks.org/html-video-height-attribute-2/)属性分别用于设置视频播放器的高度和宽度。[源](https://www.geeksforgeeks.org/html-source-tag/)标签用于指定视频、音频等多媒体资源。源标签的 [*src*](https://www.geeksforgeeks.org/html-img-src-attribute/) 属性指定了资源的路径。

**语法:**

```html
<video width=" " height=" "></video>
```

**示例 1:** 以下示例演示了根据需要设置视频的宽度和高度。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
    <title>gfg</title>
</head>
<body>
    <!-- set width and height of the video -->
<video width="800px" height="400px" controls>
    <source src="myvideo.mp4" type="video/mp4">    
</video>
</body>
</html>
```

**输出:**

<video class="wp-video-shortcode" id="video-575706-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210310182457/video.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210310182457/video.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210310182457/video.mp4)</video>

**示例 2:** 以下示例演示了如何设置视频的宽度和高度，以使您的视频响应您的屏幕宽度。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
    <title>gfg</title>
<style>
    video
    {
        position: relative;
    }
</style>
</head>
<body>
    <!-- set width and height of the video -->
<video width="100%" height="auto" controls>
    <source src="myvideo.mp4" type="video/mp4">    
</video>
</body>
</html>
```

**输出:**

<video class="wp-video-shortcode" id="video-575706-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210318163839/v.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210318163839/v.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210318163839/v.mp4)</video>