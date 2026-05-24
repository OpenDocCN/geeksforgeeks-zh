# HTML | DOM 音频结束属性

> 原文:[https://www . geesforgeks . org/html-DOM-audio-ended-property/](https://www.geeksforgeeks.org/html-dom-audio-ended-property/)

**音频结束属性**用于*返回音频播放是否已经结束*。当播放位置在音频末尾时，我们认为音频已经结束。

如果音频已经结束，Audio ended 属性返回布尔值 true，否则返回 false。音频结束属性是只读属性。

**语法:**

```html
audioObject.ended
```

下面的程序说明了音频结束属性:
**示例:**找出音频是否已经结束。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        Audio ended Property
    </title>
</head>

<body style="text-align: center">

    <h1 style="color: green">
      GeeksforGeeks
    </h1>
    <h2 style="font-family: Impact">
      Audio ended Property
    </h2>
    <br>

    <audio id="Test_Audio" controls>
        <source src="sample1.ogg" 
                type="audio/ogg">

        <source src="sample1.mp3" 
                type="audio/mpeg">
    </audio>

    <p>To find out if the audio has ended or not,
      double click the "Check Status" button.</p>
    <br>

    <button ondblclick="My_Audio()">
      Check Status
    </button>

    <p id="test"></p>

    <script>
        function My_Audio() {
            var a = 
                document.getElementById("Test_Audio").ended;
            document.getElementById("test").innerHTML = a;
        }
    </script>

</body>

</html>
```

**输出:**

*   点击按钮前:
    ![](img/a38144e8523e1db00f1d22ee2fb91001.png)
*   点击按钮后:
    ![](img/ecf3d1166b64db159068e045f7f5531d.png)

**支持的浏览器:**以下是 *HTML | DOM 音频端属性*支持的浏览器:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   苹果 Safari