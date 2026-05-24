# HTML | DOM 视频默认静音属性

> 原文:[https://www . geesforgeks . org/html-DOM-video-defaultmuted-property/](https://www.geeksforgeeks.org/html-dom-video-defaultmuted-property/)

**视频默认静音属性**用于**设置**或**返回**视频是否默认静音*。
Video defaultmuded 属性不能改变当前静音状态，它只影响默认静音状态。*

**语法:**

*   返回默认静音属性:

    ```html
    videoObject.defaultMuted
    ```

*   设置默认静音属性:

    ```html
    videoObject.defaultMuted = true|false
    ```

**属性值:**

*   **true|false:** 用于指定视频是否默认静音。

下面的程序说明了视频静音属性:
**示例:**将视频默认设置为静音。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML | DOM Video defaultMuted Property
    </title>
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
    <h2>Video defaultMuted Property</h2>
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

    <p>For muting the video by default, 
      double click the "Mute by default" button.</p>

    <button ondblclick="My_Video()"
            type="button">
      Mute by default
    </button>

    <script>
        function My_Video() {
            v.defaultMuted = true;
            v.load()
        }
    </script>

</body>

</html>
```

**输出:**

*   点击按钮前:
    ![](img/23770568c1947cb6e3065313bc554525.png)*   After clicking the button:
    ![](img/53b8d585efcf77e8586428d62f325537.png)

    **支持的浏览器:**以下是 *HTML | DOM 视频默认静音属性*支持的浏览器:

    *   谷歌 Chrome
    *   火狐浏览器
    *   歌剧
    *   苹果 Safari