# HTML | DOM Track src 属性

> 原文:[https://www.geeksforgeeks.org/html-dom-track-src-property/](https://www.geeksforgeeks.org/html-dom-track-src-property/)

**DOM 轨迹 src 属性**用于**设置**或**返回***src 属性的值，该属性显示文本轨迹*的网址。

**语法:**

*   它用于返回默认属性。

    ```html
    trackObject.src
    ```

*   它还用于设置默认属性。

    ```html
    trackObject.src = URL
    ```

**值:**

*   **URL:** 用于指定文字轨道的 URL。

**返回值:**以字符串的形式返回曲目的 URL(包括协议)。

**示例:**

```html
<html>

<head>
    <style>
        body {
            text-align: center;
        }

        h1 {
            color: green;
        }
    </style>
</head>

<body>
    <h1>GeeksforGeeks</h1>
    <h2>
      Track src Property
  </h2>

    <video width="100"
           height="100"
           controls>

        <track src=
"https://contribute.geeksforgeeks.org/wp-content/uploads/11.mp4" 
               kind="subtitles" 
               srclang="en"
               label="English">

            <source id="myTrack"
                    src=
"https://contribute.geeksforgeeks.org/wp-content/uploads/11.mp4"
                    type="video/mp4">

    </video>

    <p>
      Click the button to get
      the source of the track.
  </p>

    <button onclick="myFunction()">
        Get URL
    </button>

    <p id="gfg"></p>
    <!-- Script to get the URL property -->
    <script>
        function myFunction() {
            var x = document.getElementById(
              "myTrack");
            document.getElementById(
              "gfg").innerHTML = myTrack.src;
        }
    </script>
</body>

</html>
```

**输出:**
**点击按钮前:**
![](img/b5a71f282621b3c02fbabd1bab478c21.png)

**点击按钮后:**
![](img/a5ab15ed492c7ff04db63266239c0d76.png)

**支持的浏览器:**

*   谷歌 Chrome
*   Internet Explorer 10.0+
*   歌剧