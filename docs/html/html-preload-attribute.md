# HTML |预加载属性

> 原文:[https://www.geeksforgeeks.org/html-preload-attribute/](https://www.geeksforgeeks.org/html-preload-attribute/)

**HTML 预加载属性**用于指定页面加载时作者认为应该加载媒体的方式。
预载属性允许作者向浏览器描述网站用户体验的实现方式。

**支持的标签:**

*   [音频:预载](https://www.geeksforgeeks.org/html-audio-preload-attribute/)
*   [视频:预载](https://www.geeksforgeeks.org/html-video-preload-attribute/)

**视频预加载示例:**

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title> 
        HTML Video Preload Attribute 
    </title> 
</head> 

<body style="text-align:center"> 

    <h1 style="color:green"> 
    GeeksforGeeks 
</h1> 
    <h2 style="font-family: Impact"> 
HTML Video Preload Attribute 
</h2> 
    <br> 

    <video id="Test_Video"
        width="360"
        height="240"
        controls 
        preload="none"> 
        <source src="samplevideo.mp4"
                type="video/mp4"> 
    </video> 

</body> 

</html> 
```

**输出:**
![](img/4e7f80da24fd26c8472f0cc092613d8e.png)

**音频预载示例:**

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title> 
        HTML Audio preload Attribute 
    </title> 
</head> 

<body style="text-align: center"> 

    <h1 style="color: green"> 
    GeeksforGeeks 
</h1> 
    <h2 style="font-family: Impact"> 
HTML Audio preload Attribute 
</h2> 
    <br> 

    <audio id="Test_Audio" controls 
        preload="none"> 

        <source src="sample1.mp3"
                type="audio/mpeg"> 
    </audio> 
</body> 

</html> 
```

![](img/8b8f75d7362b4968e0f6385815c1ddfb.png)

**支持的浏览器:**HTML 视频预加载属性支持的浏览器如下

*   谷歌 Chrome 4.0
*   Firefox 4.0
*   苹果 Safari 4.0
*   歌剧 10.5