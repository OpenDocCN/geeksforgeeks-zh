# HTML | video autoplay Attribute

> 原文：[https://www.geeksforgeeks.org/html-video-autoplay-attribute/](https://www.geeksforgeeks.org/html-video-autoplay-attribute/)

The **HTML <video> autoplay attribute** is used to specify that the video will play automatically after loading the web page. It is the Boolean value, this attribute is new in HTML5.

**Syntax:**

```html
<video autoplay>
```

**Example:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>HTML video autoplay Attribute</title>
</head>

<body>
    <center>
        <h1 style="color:green;">GeeksforGeeks</h1>

        <h3>HTML video autoplay Attribute</h3>

        <video width="400" height="200" controls autoplay>
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
![](img/55398f47d320b7a46a0ddd156c0282f6.png)

**Note:** Always specify the width and the height of the video else web page will be confused that how much space that video will be required due to that reason web page become slow down.
**Supported Browsers:**

*   Google Chrome 4.0
*   Internet Explorer 9.0
*   Firefox 3.5
*   Safari 4.0
*   Opera 10.5