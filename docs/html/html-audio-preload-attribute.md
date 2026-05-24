# HTML | audio 预加载属性

> 原文:[https://www.geeksforgeeks.org/html-audio-preload-attribute/](https://www.geeksforgeeks.org/html-audio-preload-attribute/)

**HTML 音频预加载属性**用于指定页面加载时作者认为应该加载音频的方式。音频预载属性允许作者向浏览器描述实现网站用户体验的方式。

**语法:**

```html
<audio preload="auto | metadata | none">
```

**属性值:**

*   **auto:** 用于指定页面加载时浏览器应加载整个视频。
*   **元数据:**用于指定页面加载时浏览器只加载元数据。
*   **无:**用于指定页面加载时浏览器不应加载视频。

**示例:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML Audio preload Attribute
    </title>
</head>

<body style="text-align: center">

    <h1 style="color: green"> 
    GeeksforGeeks 
</h1>
    <h2 style="font-family: Impact"> 
HTML Audio preload Attribute 
</h2>
    <br>

    <audio id="Test_Audio" controls 
           preload="none">

        <source src="sample1.mp3" 
                type="audio/mpeg">
    </audio>
</body>

</html>
```

**输出:**
![](img/8b8f75d7362b4968e0f6385815c1ddfb.png)

**支持的浏览器:****HTML 音频预加载属性**支持的浏览器如下:

*   谷歌 Chrome 4.0
*   Internet Explorer 9.0
*   Firefox 4.0
*   苹果 Safari 4.0
*   歌剧 10.5