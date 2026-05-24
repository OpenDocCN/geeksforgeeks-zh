# HTML | DOM 视频加载( )方法

> 原文:[https://www.geeksforgeeks.org/html-dom-video-load-method/](https://www.geeksforgeeks.org/html-dom-video-load-method/)

**视频加载()方法**用于重新加载视频元素。视频加载()方法用于在更改源或其他设置后更新视频元素。
视频加载()方法不接受任何参数，也不返回值。
**语法:**

```html
videoObject.load()
```

下面的程序说明了视频加载()方法:
**示例:**更改视频源并重新加载视频。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        DOM Video load( ) Method
    </title>
</head>

<body style="text-align:center">

    <h1 style="color:green">
      GeeksforGeeks
    </h1>
    <h2 style="font-family: Impact">
      Video load method
    </h2>
    <br>

    <video id="Test_Video"
           width="360"
           height="240"
           controls>

        <source id="mp4_source"
                src="sample2.mp4"
                type="video/mp4">

        <source id="ogg_source"
                src="sample2.ogg"
                type="video/ogg">
    </video>

<p>To change the source of the video
      and re-load it, double click the
      "Change Source" button.</p>

    <br>

    <button ondblclick="My_Video()">
      Change Source
    </button>

    <script>
        function My_Video() {
            document.getElementById("mp4_source").src =
              "samplevideo.mp4";
            document.getElementById("ogg_source").src =
              "samplevideo.ogg";
            document.getElementById("Test_Video").load();
        }
    </script>

</body>

</html>
```

**输出:**

*   点击按钮前:

![](img/4eda817bd9c051da82c611de51a0b98b.png)

*   点击按钮后:

![](img/879a2b2b463c2c2048ecce6ed64b0c3f.png)

**支持的浏览器:**以下列出 *HTML | DOM 视频加载( )方法*
支持的浏览器:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   苹果 Safari