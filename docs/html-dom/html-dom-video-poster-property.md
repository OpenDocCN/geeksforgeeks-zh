# HTML | DOM 视频海报属性

> 原文:[https://www . geesforgeks . org/html-DOM-video-poster-property/](https://www.geeksforgeeks.org/html-dom-video-poster-property/)

视频海报属性用于**设置**或**返回** *视频*海报属性的值。海报属性专门用于在下载视频时或用户点击播放按钮之前显示图像。
如果不包括海报选项，则显示视频的第一帧。

**语法:**
**返回海报属性:**

```html
videoObject.poster
```

**设置海报属性:**

```html
videoObject.poster = URL
```

**属性值**

*   **URL :** 用于指定图像文件的 URL。

以下程序说明了视频海报属性:

**示例:**更改视频的海报图像。

```html
<!DOCTYPE html>
<html>

<head>
  <title>DOM Video poster Property</title>
</head>

<body style="text-align:center">

    <h1 style="color:green">
      GeeksforGeeks
  </h1>
    <h2 style="font-family: Impact">
      Video Poster Property
  </h2>
    <br>

    <video id="Test_Video" 
           width="360" 
           height="240" 
           poster="gfg_200X200.png" 
           controls>

        <source src="samplevideo.mp4"
                type="video/mp4">
        <source src="movie.ogg" 
                type="video/ogg">
    </video>

    <p>To change the poster image,
      double click the "Change Poster" button.</p>

    <button ondblclick="My_Video()"
            type="button">Change Poster</button>

    <script>
        function My_Video() {
            document.getElementById(
              "Test_Video").poster = "Unknown.png";
        }
    </script>

</body>

</html>
```

**输出:**
**点击按钮前:**
![](img/00427ff98f3101654455db47c78caff0.png)

**点击按钮后:**
![](img/65ad5ff54b90b335b5b0ca6386869827.png)

**支持的浏览器:**

*   苹果 Safari
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   谷歌 Chrome
*   歌剧