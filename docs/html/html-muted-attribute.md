# HTML |静音属性

> 原文:[https://www.geeksforgeeks.org/html-muted-attribute/](https://www.geeksforgeeks.org/html-muted-attribute/)

**HTML 静音属性**用于*指定视频的音频输出为静音*，是布尔属性。
**适用:**

*   [<视频静音属性>](https://www.geeksforgeeks.org/html-video-muted-attribute/?ref=rp)

**语法**

```html
<video muted>
```

**例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML muted Attribute
    </title>
</head>

<body style="text-align: center">

    <h1 style="color:green">
    GeeksforGeeks
</h1>
    <h2 style="font-family:Impact">
    HTML muted Attribute
</h2>
    <br>

    <video id="Test_Video"
        width="360"
        height="240"
        controls muted>

        <source src="samplevideo.mp4"
                type="video/mp4">

        <source src="samplevideo.ogg"
                type="video/ogg">
    </video>
</body>

</html>
```

**输出:**

![](img/d7e2614aaaa2dc80797e7e1d8d77d892.png)

**支持的浏览器:****HTML 静音属性**支持的浏览器如下:

*   谷歌 Chrome 4.0
*   Internet Explorer 10.0
*   Firefox 11.0
*   苹果 Safari 7.1
*   歌剧 10.5