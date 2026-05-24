# 如何在 HTML 5 中设置视频上的缩略图？

> 原文:[https://www . geesforgeks . org/如何在 html-5 中设置视频缩略图/](https://www.geeksforgeeks.org/how-to-set-the-thumbnail-image-on-video-in-html-5/)

**简介:**在本文中，我们将学习如何为 HTML5 视频设置缩略图。缩略图是显示为视频预览的图像。基本上它是用来表示视频包含的内容或与视频相关的内容。它一直显示到视频开始。默认情况下，视频的第一帧显示为视频的初始预览。

**方法:**有时用户想要显示他选择的特定图像作为视频的缩略图。这可以简单地通过使用海报属性来完成。你所要做的就是在视频标签中创建一个海报属性，并在其中放置缩略图的网址。

**语法:**

```html
<video height="" width="" poster="URL of the image to be displayed">
```

**示例:**

```html
<!DOCTYPE html>
<html>

<body>

    <video width="400" 
           height="350" 
           controls poster=
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190710102234/download3.png">
        <source src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200409094356/Placement100-_-GeeksforGeeks2.mp4"
                type="video/mp4">
    </video>
</body>

</html>
```

**输出:**

<video class="wp-video-shortcode" id="video-395009-1" width="640" height="360" poster="https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190710102234/download3.png" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200409094356/Placement100-_-GeeksforGeeks2.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200409094356/Placement100-_-GeeksforGeeks2.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200409094356/Placement100-_-GeeksforGeeks2.mp4)</video>

**说明:**视频标签的海报属性包含用户想要设置为视频缩略图的图像的 URL，该图像是在用户按下播放按钮之前将可见的图像。src 属性包含视频的 URL，控制属性显示视频中的播放/暂停/搜索/音量等功能。

关于 HTML 视频标签的更多信息，请访问[这里](https://www.geeksforgeeks.org/html5-video/)