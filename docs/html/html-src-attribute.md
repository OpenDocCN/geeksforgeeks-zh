# HTML src 属性

> 原文:[https://www.geeksforgeeks.org/html-src-attribute/](https://www.geeksforgeeks.org/html-src-attribute/)

html src 属性用于指定外部资源的位置(URL)。

**支持的标签:**

*   [<音频>](https://www.geeksforgeeks.org/html-audio-src-attribute/)
*   [<嵌入>](https://www.geeksforgeeks.org/html-embed-src-attribute/)
*   [< iframe >](https://www.geeksforgeeks.org/html-iframe-src-attribute/)

*   <【img】>
*   [<输入>](https://www.geeksforgeeks.org/html-input-src-attribute/)
*   [<剧本>](https://www.geeksforgeeks.org/html-script-src-attribute/)
*   [<来源>](https://www.geeksforgeeks.org/html-source-src-attribute/)
*   [<赛道>](https://www.geeksforgeeks.org/html-track-src-attribute/)
*   [<视频>](https://www.geeksforgeeks.org/html-video-src-attribute/)

**属性值:**包含单值 URL，指定源文件的链接。下面列出了两种类型的网址链接:

*   **绝对 URL** :指向另一个网页。
*   **相对 URL:** 指向同一网页的其他文件。

**示例:** HTML 音频 src 属性

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML audio src Attribute
    </title>
</head>

<body style="text-align:center;">

    <h1>GeeksforGeeks</h1>

    <h2>
        HTML audio src Attribute
    </h2>

    <audio controls muted>
        <source src="GFG.mp3" type="audio/mp3">
        <source src="GFG.ogg" type="audio/ogg">
    </audio>
</body>

</html>                    
```

**输出:**

![](img/7f95d3e1e74c2171b0e56efe43bb0154.png)

**示例:** HTML img src 属性

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML img src Attribute
    </title>
</head>

<body>
    <h1>GeeksforGeeks</h1>

    <h2>HTML img src Attribute</h2>

    <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190506164011/logo3.png"
        alt="GeeksforGeeks logo">
</body>

</html>
```

**输出:**

![](img/96a28035b0307b530c37cb84c5497424.png)

**支持的浏览器:****HTML src 属性**支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   苹果 Safari
*   歌剧