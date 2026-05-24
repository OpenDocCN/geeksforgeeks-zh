# HTML | video preload Attribute

> 原文：[https://www.geeksforgeeks.org/html-video-preload-attribute/](https://www.geeksforgeeks.org/html-video-preload-attribute/)

The **HTML audio preload Attribute** is used to specify the way the author thinks the video should be loaded when the page loads.

The video preload attribute allows the author to portray to the browser about the way the user experience of a website should be implemented.
**Syntax:**

```html
<video preload="auto | metadata | none"> 
```

**Attribute Values:**

*   **auto:** It is used to specify that the browser should load the entire video when the page loads.
*   **metadata:** It is used to specify that the browser should load only metadata when the page loads.
*   **none:** It is used to specify that the browser should NOT load the video when the page loads.

**Example:**

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
HTML  Video Preload Attribute 
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

**Output:**
![](img/4e7f80da24fd26c8472f0cc092613d8e.png)

**Supported Browsers:** The browsers supported by **HTML video preload Attribute** are listed below:

*   Google Chrome 4.0
*   Firefox 4.0
*   Apple Safari 4.0
*   Opera 10.5