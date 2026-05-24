# HTML | DOM 音频查找属性

> 原文:[https://www . geesforgeks . org/html-DOM-audio-seeking-property/](https://www.geeksforgeeks.org/html-dom-audio-seeking-property/)

**DOM 音频查找属性**用于用户当前在音频中查找时返回*。当用户移动或跳到音频中的新位置时，称为**寻找**。*

**语法:**

```html
audioObject.seeking
```

**返回:**如果用户当前正在搜索，音频搜索属性返回布尔值 true，否则返回 false。音频搜索属性是只读属性。

下面的程序说明了音频搜索属性:
**示例:**显示用户当前是否在视频中搜索。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        Audio seeking Property
    </title>
</head>

<body style="text-align:center">

    <h1 style="color:green">
      GeeksforGeeks
    </h1>
    <h2 style=" font-family: Impact">
      Audio seeking Property
    </h2>
    <br>

    <audio id="Test_Audio"
           controls onseeking="MyAudio()"
           onseeked="MyAudio()">

        <source src="sample1.ogg" 
                type="audio/ogg">

        <source src="sample1.mp3" 
                type="audio/mpeg">
    </audio>

    <p>Try seeking the audio to know the state
      <span id="Test_Span"></span></p>
    <br>

    <p id="test"></p>

    <script>
        function MyAudio() {
            var a = document.getElementById("Test_Audio");
            document.getElementById("Test_Span").innerHTML = 
              ("Seeking: " + a.seeking);
        }
    </script>

</body>

</html>
```

**输出:**

*   点击按钮前:
    ![](img/a38c553d5f31792ecb3f8299abafbf52.png)
*   点击按钮后:
    ![](img/a343da829d446a67f0e8d9dfa6a76a0d.png)

**支持的浏览器:***DOM 音频搜索属性*支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   苹果 Safari