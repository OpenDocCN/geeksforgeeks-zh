# HTML |控件属性

> 原文:[https://www.geeksforgeeks.org/html-controls-attribute/](https://www.geeksforgeeks.org/html-controls-attribute/)

**HTML 控件属性**用于指定必须显示音频和视频控件。这是一个布尔属性，在 HTML5 中也是新的。我们可以在两个标签中使用这个属性<音频>和<视频>

控件属性包括

<audio>标签上的以下属性:</audio>

*   玩
*   中止
*   寻找
*   卷

控件属性包括<video>标签上的以下属性:</video>

*   玩
*   中止
*   寻找
*   卷
*   全屏切换(仅适用于视频)
*   字幕/字幕(仅适用于视频，如果有)
*   轨道(仅用于视频，如果可用)

**语法:**

```html
<element controls> 
```

下面的例子说明了在

<audio>元素中控件属性的使用。</audio>

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

    <audio id="Test_Audio" controls autoplay>

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

下面的例子说明了在<video>元素中控件属性的使用。</video>

**示例:**

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title>HTML video controls Attribute</title> 
</head> 

<body> 
    <center> 
        <h1 style="color:green;">GeeksforGeeks</h1> 

        <h3>HTML video controls Attribute</h3> 

        <video width="400" height="200" controls > 
            <source src= 
"https://media.geeksforgeeks.org/wp-content/uploads/20190616234019/Canvas.move_.mp4"
                    type="video/mp4"> 
            <source src= 
"https://media.geeksforgeeks.org/wp-content/uploads/20190616234019/Canvas.move_.ogg"
                    type="video/ogg"> 
        </video> 
    </center> 
</body> 

</html> 
```

**输出:**
![](img/cef0c0d0671ac0ffe2dd620b65285cf6.png)

**支持的浏览器:**HTML 控件属性支持的浏览器如下:

*   谷歌 Chrome 4.0
*   Internet Explorer 9.0
*   Firefox 3.5
*   Safari 4.0
*   歌剧 10.5