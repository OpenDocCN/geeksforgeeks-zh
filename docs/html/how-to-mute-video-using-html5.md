# 如何使用 HTML5 将视频静音？

> 原文:[https://www . geesforgeks . org/how-mute-video-use-html 5/](https://www.geeksforgeeks.org/how-to-mute-video-using-html5/)

本文的目的是使用 HTML5 将视频静音。

**进场:**

视频标签是 HTML5 的新功能。用户可以在视频标签中使用 [**静音**](https://www.geeksforgeeks.org/html-video-muted-attribute/) 属性来静音一个视频。

静音属性是布尔属性。存在时，它指定视频的音频输出应静音。

**语法:**

```html
<video controls muted>
```

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<body>
  <h1>Muted Video</h1>
 <!-- Video mute -->
 <video controls muted width="600px">
   <source src="https://media.geeksforgeeks.org/wp-content/uploads/20210506112845/GFG1.mp4" type="video/mp4">
  </video>
</body>
</html>
```

**输出:**

![](img/cba09940bd00b287ba7bfc1681155720.png)