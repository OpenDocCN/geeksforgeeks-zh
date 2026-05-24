# HTML | DOM 视频 src 属性

> 原文:[https://www.geeksforgeeks.org/html-dom-video-src-property/](https://www.geeksforgeeks.org/html-dom-video-src-property/)

**视频 src 属性**用于**设置**或**返回** *视频*的 src 属性值。
src 属性一般用于指定视频文件的位置(URL)。

**语法:**

*   返回 src 属性:

    ```html
    videoObject.src
    ```

*   设置 src 属性:

    ```html
    videoObject.src = URL
    ```

**属性值:**

*   **URL:** 用于指定视频文件的 URL。

**返回值:**Video src 属性返回一个字符串，代表视频文件的 URL。src 属性返回整个 URL，包括协议。

下面的程序说明了视频 src 属性:

**示例:**更改视频的 URL。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        DOM Video src Property
    </title>
</head>

<body style="text-align: center">

    <h1 style="color: green">GeeksforGeeks</h1>
    <h2 style="font-family: Impact">Video src Property</h2>
    <br>

    <video id="Test_Video"
           width="360"
           height="240"
           controls src="sample video.ogg">
    </video>

    <p>To change the Url of the video,
      double click the "Change URL" button.
        <br>

        <button ondblclick="My_Video()">
          Change URL
      </button>

        <p id="test"></p>

        <script>
            var v = document.getElementById("Test_Video");

            function My_Video() {
                isSupp = v.canPlayType("video/mp4");
                if (isSupp == "") {
                    v.src = "sample2.ogg";
                } else {
                    v.src = "sample2.mp4";
                }
                v.load();

                document.getElementById("test").innerHTML = 
                "Video Courtesy - www.geeksforgeeks.org";
            }
        </script>

</body>

</html>
```

**输出:**

*   点击按钮前:
    ![](img/df32220fac3dce0917bc6ebdefd252ca.png)
*   点击按钮后:
    ![](img/febd9c03b43be10e0ec5fb1e94263be4.png)

**支持的浏览器:**以下是 *HTML | DOM Video src Property* 支持的浏览器:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   苹果 Safari