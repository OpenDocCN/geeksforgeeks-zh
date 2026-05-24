# HTML embed 标签

> 原文:[https://www.geeksforgeeks.org/html-embed-tag/](https://www.geeksforgeeks.org/html-embed-tag/)

HTML 中的<embed>标记用于将外部应用程序嵌入到 HTML 文档中，这些外部应用程序通常是音频或视频等多媒体内容。它被用作嵌入插件(如 flash 动画)的容器。这个标签是 HTML 5 中的一个新标签，它只需要一个起始标签。

**语法:**

```html
<embed attributes>
```

**属性:**<嵌入的>标签包含以下讨论的四个属性:

*   [**高度**](https://www.geeksforgeeks.org/html-height-attribute/) **:** 该属性包含以像素为单位的属性值。它用于指定嵌入内容的高度。
*   [**src**](https://www.geeksforgeeks.org/html-src-attribute/) **:用于保存网址。它用于指定嵌入内容的网址。**
*   [**宽度**](https://www.geeksforgeeks.org/css-width-property/) **:** 宽度值以像素为单位设置。它用于指定嵌入内容的宽度。
*   [**类型**](https://www.geeksforgeeks.org/html-type-attribute/) **:** 它包含了 media_type 内容。它用于指定嵌入内容的媒体类型。

下面的程序说明了 HTML 中的<embed>元素:

**例 1:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
    <head>
        <title>embed Tag</title>
        <style>
            q {
                color: #00cc00;
                font-style: italic;
            }
        </style>
    </head>
    <body>
        <q>GeeksforGeeks</q> is loading.
        <br>
        <embed src="loading2.swf"
        type="application/x-shockwave-flash">
    </body>
</html>                   
```

**输出:**

<video class="wp-video-shortcode" id="video-247119-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/Screen-Recording-2018-11-21-at-3.32.35-PM.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/Screen-Recording-2018-11-21-at-3.32.35-PM.mp4](https://media.geeksforgeeks.org/wp-content/uploads/Screen-Recording-2018-11-21-at-3.32.35-PM.mp4)</video>

**示例 2:** 本示例使用带有<嵌入>标签的宽度和高度属性。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
    <head>
        <title>embed Tag</title>
        <style>
            q {
                color: #00cc00;
                font-style: italic;
            }
        </style>
    </head>
    <body>
        Click here to redirect to <q>GeeksforGeeks</q>
        <br>
        <embed src="animProps02.swf" width="30px" height="30px">
        <a href="http://geeksforgeeks.org">GeeksforGeeks</a>
    </body>
</html>                             
```

**输出:**

<video class="wp-video-shortcode" id="video-247119-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/Screen-Recording-2018-11-21-at-3.26.36-PM.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/Screen-Recording-2018-11-21-at-3.26.36-PM.mp4](https://media.geeksforgeeks.org/wp-content/uploads/Screen-Recording-2018-11-21-at-3.26.36-PM.mp4)</video>

**支持的浏览器:**

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队