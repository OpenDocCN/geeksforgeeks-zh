# HTML | video poster Attribute

> 原文：[https://www.geeksforgeeks.org/html-video-poster-attribute/](https://www.geeksforgeeks.org/html-video-poster-attribute/)

The **HTML <video> poster Attribute** is used to display the image while video downloading or when user click the play button. If this image not set then it will take the first frame of video as a poster image.

**Syntax:**

```html
<video poster="URL">
```

**Attribute Values:** It contains a single value URL which specifies the link of source image. There are two types of URL link which are listed below:

*   **Absolute URL:** It points to another webpage.
*   **Relative URL:** It points to other files of the same web page.

**Example:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>HTML video poster Attribute</title>
</head>

<body>
    <center>
        <h1 style="color:green;">GeeksforGeeks</h1>

        <h3>HTML video poster Attribute</h3>

        <video width="400" height="200" controls poster=
"https://media.geeksforgeeks.org/wp-content/uploads/20190627130930/a218.png">
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
![](img/896294be923a8b6369dba4a492be1856.png)

**Note:** Always specify the width and the height of the video else web page will be confused that how much space that video will be required due to that reason web page become slow down.

**Supported Browsers:** The browser supported by HTML <video> poster Attribute are listed below:

*   Google Chrome 4.0
*   Internet Explorer 9.0
*   Firefox 3.6
*   Safari 4.0
*   Opera 10.5