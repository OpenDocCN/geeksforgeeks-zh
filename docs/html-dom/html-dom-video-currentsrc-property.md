# HTML | DOM 视频流属性

> 原文:[https://www . geesforgeks . org/html-DOM-video-current src-property/](https://www.geeksforgeeks.org/html-dom-video-currentsrc-property/)

**视频流属性**用于*返回当前视频*的网址。如果未指定视频，则 Video currentSrc 属性返回一个空字符串。
videoccurrentsrc 属性是只读属性。

**语法:**

```html
videoObject.currentSrc
```

下面的程序说明了视频当前的属性:
**示例:**获取当前视频的网址。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML | DOM Video currentSrc Property
    <title>
    <style>
        h1 {
            color: green;
        }

        h2 {
            font-family: Impact;
        }

        body {
            text-align: center;
        }
    </style>
</head>

<body>

    <h1>GeeksforGeeks</h1>
    <h2>Video currentSrc Property</h2>
    <br>

    <video id="Test_Video" 
           width="360"
           height="240" 
           controls>
        <source src="samplevideo.mp4" 
                type="video/mp4">
        <source src="movie.ogg"
                type="video/ogg">
    </video>

    <p>
      To get the video URL, 
      double click the "Return URL" button.
    </p>

    <button ondblclick="My_Video()" 
            type="button">
      Return URL
    </button>

    <p id="test"></p>

    <script>
        function My_Video() {
            var v =
                document.getElementById(
              "Test_Video").currentSrc;
            document.getElementById("test").innerHTML = v;
        }
    </script>

</body>

</html>
```

**输出:**

*   点击按钮前:
    ![](img/b81a1916d2e1f71fc79b9c5099aca015.png)
*   点击按钮后:
    ![](img/7798476019d02c946239971169539004.png)

**支持的浏览器:**以下是 *HTML | DOM 视频流属性*支持的浏览器:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   苹果 Safari