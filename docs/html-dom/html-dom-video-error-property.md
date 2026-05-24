# HTML | DOM 视频错误属性

> 原文:[https://www . geesforgeks . org/html-DOM-video-error-property/](https://www.geeksforgeeks.org/html-dom-video-error-property/)

**DOM 视频错误属性**用于返回 MediaError 对象，MediaError 对象包含视频的错误状态。

**语法:**

```html
video.error.code
```

**返回类型:**该属性返回一个**数字**，代表视频的错误状态:

*   1 =媒体 _ 错误 _ 中止–用户中止了提取过程
*   2 =媒体 _ 错误 _ 网络–下载时出错
*   3 = MEDIA _ ERR _ DECODE–解码时出错
*   4 = MEDIA _ ERR _ SRC _ NOT _ SUPPORTED–不支持视频

**示例:**

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title> 
        Video error Property 
    </title> 
</head> 

<body style="text-align: center"> 

    <h1 style="color: green"> 
        GeeksforGeeks 
    </h1>

    <h2 style="font-family: Impact"> 
        Video error Property 
    </h2> 
    <br> 

    <video id="Test_Video" width="360"
        height="240" controls> 

        <source id="mp4_source" src="sample2.mp4"
                type="video/mp4"> 

        <source id="ogg_source" src="sample2.ogg"
                type="video/ogg"> 
    </video> 
    <br> 

    <button ondblclick="My_Video()"> 
        Return Error State
    </button> 

    <p id="test"></p> 

    <script> 
        function My_Video() { 
            var v = document.getElementById( 
                   "Test_Video").error.code; 

            document.getElementById("test"
                   ).innerHTML = v; 
        } 
    </script> 
</body> 

</html>
```

**输出:**
![](img/9e20e7472e99f71e282110ae414492b7.png)

**支持的浏览器:****HTML DOM 视频错误属性**支持的浏览器如下:

*   微软公司出品的 web 浏览器