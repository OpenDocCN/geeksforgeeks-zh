# HTML | video height Attribute

> 原文：[https://www.geeksforgeeks.org/html-video-height-attribute-2/](https://www.geeksforgeeks.org/html-video-height-attribute-2/)

The **HTML <video> height Attribute** is used to set the height of video player in terms of pixels. This attribute is new in HTML5.

**Syntax:**

```html
<video height="pixels">
```

**Attribute Values:** It contains single value pixels which set the height of video frame.

**Example:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>HTML video height Attribute</title>
</head>

<body>
    <center>
        <h1 style="color:green;">GeeksforGeeks</h1>

        <h3>HTML video height Attribute</h3>

        <video width="400" height="200" controls>
            <source src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190616234019/Canvas.move_.mp4" 
                                type="video/mp4">
            <source src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190616234019/Canvas.move_.ogg" 
                                type="video/ogg">
        </video>
  </center>
</body>

</html>
```

**Output:**
![](img/73250a6c0f04b48988a82c729f021d5a.png)
**Note:** Downsizing a large size video with the height and width attributes forces users to download the original video. The best way to rescale videos is with a program, before using it on a page.

**Supported Browsers:** The browser supported by HTML <video> height Attribute are listed below:

*   Google Chrome
*   Internet Explorer
*   Firefox
*   Safari
*   Opera