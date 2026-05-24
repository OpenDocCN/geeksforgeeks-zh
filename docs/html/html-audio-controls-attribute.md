# HTML | audio 控制属性

> 原文:[https://www . geesforgeks . org/html-audio-controls-attribute/](https://www.geeksforgeeks.org/html-audio-controls-attribute/)

**HTML <音频>控件属性**用于指定播放音频的控件。它是布尔值。这个属性在 HTML5 中是新的。

音频控制属性包含以下属性:

*   玩
*   中止
*   寻找
*   卷

**语法:**

```html
<audio controls>
```

**示例:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML Audio controls Attribute
    </title>
</head>

<body style="text-align: center">

    <h1 style="color: green"> 
        GeeksforGeeks 
    </h1>

    <h2 style="font-family: Impact"> 
        HTML Audio controls Attribute 
    </h2>
    <br>

    <audio id="Test_Audio" controls>

        <source src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190531165842/Recording1514.ogg"
                type="audio/ogg">

        <source src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190531165842/Recording1514.mp3"
                type="audio/mpeg">
    </audio>
</body>

</html>                    
```

**输出:**
![](img/09967b733dc0ebb560faadca95fd56ab.png)

**支持的浏览器:**HTML<音频>控件属性支持的浏览器如下:

*   谷歌 Chrome 4.0
*   Internet Explorer 9.0
*   Firefox 3.5
*   Safari 4.0
*   歌剧 10.5