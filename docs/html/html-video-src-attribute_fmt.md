
# HTML | video src Attribute

> 原文：[https://www.geeksforgeeks.org/html-video-src-attribute/](https://www.geeksforgeeks.org/html-video-src-attribute/)

The **HTML `<video>` src Attribute** is used to specify the URL of the video file. This attribute uses Ogg file on Firefox, Opera, and Chrome browsers and MPEG4 file on Internet Explorer and Safari browsers. This attribute is new in HTML5.

**Syntax:**

```html
<video src="URL">
```

**Attribute Values:** It contains a single value URL which specifies the link of the source video. There are two types of URL links which are listed below:

*   **Absolute URL:** It points to another webpage.
*   **Relative URL:** It points to other files of the same web page.

**Example:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>HTML video src Attribute</title>
</head>

<body>
    <center>
        <h1 style="color:green;">GeeksforGeeks</h1>

<h3>HTML video src Attribute</h3>

<video width="400" height="200" controls src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190616234019/Canvas.move_.mp4">
         Browser not supported
        </video>
    </center>
</body>

</html>
```

**Output:**
![](img/e93a12fe6cbc9722f3fa4713b6ebfaff.png)

**Note:** Always specify the width and the height of the video; otherwise, the web page will be confused about how much space the video will require, due to which the web page may become slow.

**Supported Browsers:** The browsers supported by the HTML `<video>` src Attribute are listed below:

*   Google Chrome 4.0
*   Internet Explorer 9.0
*   Firefox 3.5
*   Safari 4.0
*   Opera 10.5
