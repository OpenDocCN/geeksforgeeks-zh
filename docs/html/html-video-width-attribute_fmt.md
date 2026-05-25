
# HTML video width Attribute

> 原文：[https://www.geeksforgeeks.org/html-video-width-attribute/](https://www.geeksforgeeks.org/html-video-width-attribute/)

The **HTML video width Attribute** is used to specify the width of the video player in terms of pixels. Always specify the width and the height of the video; otherwise, the web page will be confused about how much space the video will require, which may cause the page to slow down.

**Syntax:**

```html
<video width="pixels">
```

**Attribute Values:**

*   **pixels:** It specifies the width of the video player in terms of pixels.

**Note:** Downsizing a large video with the height and width attributes forces users to download the original video. The best way to rescale videos is to use a program before using them on a page.

Below Example illustrates the use of the width attribute in the `<video>` Element.
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
        <source src="gfg.mp4" type="video/mp4">
    </video>

</body>

</html>
```

**Output:**
![](img/c21c6ec916c7244a47b69ade1314a42a.png)

**Supported Browsers:** The browsers supported by the HTML video width Attribute are listed below:

*   Google Chrome
*   Internet Explorer 9.0 or above
*   Firefox
*   Safari
*   Opera
