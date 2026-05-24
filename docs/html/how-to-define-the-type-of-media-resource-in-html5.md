# 如何定义 HTML5 中的媒体资源类型？

> 原文:[https://www . geesforgeks . org/如何定义 html5 中的媒体资源类型/](https://www.geeksforgeeks.org/how-to-define-the-type-of-media-resource-in-html5/)

我们可以通过 [**<源>**](https://www.geeksforgeeks.org/html-source-tag/) 标签在 HTML 中定义或指定媒体文件(音频、视频等)的类型。它定义了多媒体资源，并为浏览器提供了该媒体文件的多种可选类型，浏览器可以根据其与该媒体类型的兼容性从中进行选择。

**注意:**浏览器从给定类型中选择其支持的第一种媒体类型。

**语法:**

```html
<source src="<media_file>.<media_file_extension>" type="<media_type>">
```

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Defining media types</title>
  </head>
  <body>
    <h2>Welcome To GeeksforGeeks</h2>

    <audio controls>
      <source src="sound.wav" type="audio/ogg" />
      <source src="sound.mp3" type="audio/mpeg" />
    </audio>
  </body>
</html>
```

**输出:**

![](img/bd425c338d5d0632a06c3c074838cadb.png)

sound.wav

在该示例中，两种类型的音频文件包括两个源标签，即 **'** *wav* **'** 和 *mp3* **'** 。如果浏览器支持 *wav* 音频文件，它将只播放该来源的音频，如果不支持，它将检查下一个给定选项，即 *mp3* 音频类型。

如果没有任何音频类型与浏览器兼容，则不会选择任何音频源。否则，顺序中的第一个音频类型将被选为音频源。并且，*类型*是定义资源类型的属性。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
  <head>
    <meta name="viewport"
          content="width=device-width, initial-scale=1.0" />
  </head>
  <body>
    <h1 style="color: green">
     GeeksforGeeks
    </h1>

    <picture>
      <source srcset="gfg.png" />
      <source srcset="gfg.jpg" />
      <img src="gfg.jpg" />
    </picture>
  </body>
</html>
```

**输出:**

![](img/176f252885fe69aa39b728bdb8d62246.png)

gfg.png