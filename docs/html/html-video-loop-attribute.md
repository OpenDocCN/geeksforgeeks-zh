# HTML | video loop Attribute

> 原文：[https://www.geeksforgeeks.org/html-video-loop-attribute/](https://www.geeksforgeeks.org/html-video-loop-attribute/)

The **HTML <video> loop Attribute** is used to restart the video again and again after finishing it. It contains the Boolean value. This tag is new in HTML5.

**Syntax:**

```html
<video loop>
```

**Example:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>HTML video loop Attribute</title>
</head>

<body>
    <center>
        <h1 style="color:green;">GeeksforGeeks</h1>

        <h3>HTML video loop Attribute</h3>

        <video width="400" height="200" controls loop>
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
</html> 
```

**Output:**
![](img/586a0100c9b014fb486f1f037ffd5906.png)
**Note:** Always specify the width and the height of the video else web page will be confused that how much space that video will be required due to that reason web page become slow down.

**Supported Browsers:** The browser supported by HTML <video> loop Attribute are listed below:

*   Google Chrome 4.0
*   Internet Explorer 9.0
*   Firefox 11.0
*   Safari 4.0
*   Opera 10.5