# 如何使用 HTML5 将视频静音？

> 原文: [https://www.geeksforgeeks.org/how-to-mute-video-using-html5/](https://www.geeksforgeeks.org/how-to-mute-video-using-html5/)

本文的目的是使用 HTML5 将视频静音。

## 进场

`<video>`标签是 HTML5 的新功能。用户可以在`<video>`标签中使用[`muted`](https://www.geeksforgeeks.org/html-video-muted-attribute/)属性来静音一个视频。

`muted`属性是布尔属性。存在时，它指定视频的音频输出应静音。

## 语法

`<video controls muted>`

## 示例

### 超文本标记语言

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

## 输出

![](img/cba09940bd00b287ba7bfc1681155720.png)