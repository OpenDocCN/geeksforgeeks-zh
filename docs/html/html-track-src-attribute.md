# HTML | track src Attribute

> 原文：[https://www.geeksforgeeks.org/html-track-src-attribute/](https://www.geeksforgeeks.org/html-track-src-attribute/)

The **HTML <track> src Attribute** is used to specify the URL of the track.

**Syntax:**

```html
<track src="subtitles_en.vtt">
```

**Attribute Values:** It contains single value **URL** which is used to specify the URL of the track.

Below example illustrates the use of src attribute in <track> element.

**Example:**

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        body {
            text-align: center;
        }

        h1 {
            color: green;
        }
    </style>
</head>

<body>
    <h1>GeeksforGeeks</h1>
    <h3> HTML Track src Attribute </h3>

    <video width="400" height="200" controls>

        <track src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190626010302/ice_video_20190626-005104_edit_0.mp4" 
               kind="subtitles" srclang="en" label="English">

            <source id="myTrack" src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190626010302/ice_video_20190626-005104_edit_0.mp4" 
                                            type="video/mp4">
    </video>
</body>

</html>
```

**Output:**
![](img/05ca26ac862679e2e9dadbba10a615e3.png)

**Supported Browsers:** The browser supported by HTML <track> src Attribute are listed below:

*   Google Chrome 18.0
*   Internet Explorer 10.0
*   Firefox 31.0
*   Safari 6.0
*   Opera 15.0