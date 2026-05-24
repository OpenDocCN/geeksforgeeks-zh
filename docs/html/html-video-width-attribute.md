# HTML video width Attribute

> 原文：[https://www.geeksforgeeks.org/html-video-width-attribute/](https://www.geeksforgeeks.org/html-video-width-attribute/)

The **HTML video width Attribute** is used to specify the width of the video player in terms of pixels. Always specify the width and the height of the video else web page will be confused that how much space that video will be required due to that reason web page become slow down.

**Syntax:**

```html
<video width="pixels">
```

**Attribute Values:**

*   **pixels:** It specify the width of the video player in terms of pixels.

**Note:** Downsizing a large size video with the height and width attributes forces users to download the original video. The best way to rescale videos is with a program, before using it on a page.

Below Example illustrates the use of width attribute in <video> Element.
**Example:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML video width Attribute
    </title>
</head>

<body style="text-align: center">

    <h1 style="color: green"> 
        GeeksforGeeks 
    </h1>

    <h3> 
        HTML Video width Attribute
    </h3>
    <br>

    <video id="Test_Video" width="400" height="240" controls>
        <source src = "gfg.mp4" type = "video/mp4">
    </video>

</body>

</html>                    
```

**Output:**
![](img/c21c6ec916c7244a47b69ade1314a42a.png)

**Supported Browsers:** The browser supported by HTML video width Attribute are listed below:

*   Google Chrome
*   Internet Explorer 9.0 or above
*   Firefox
*   Safari
*   Opera