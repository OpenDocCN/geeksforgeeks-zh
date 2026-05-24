# HTML | track srclang Attribute

> 原文：[https://www.geeksforgeeks.org/html-track-srclang-attribute/](https://www.geeksforgeeks.org/html-track-srclang-attribute/)

The **HTML <track> srclang Attribute** is used to *specify the language of the track text*. The srclang attribute can be applied on the **<track>** element:

**Note:** srclang attribute is required with *kind = “subtitles”*.

**Syntax:**

```html
<track src="subtitles_en.vtt" kind="subtitles" srclang="en"> 
```

**Attribute Values**

*   **language_code:** It contains the value i.e **language_code** It defines a two-letter language code which specify the language of the track text.

**Example:**

```html
<html>

<head>
</head>

<body style="text-align: center">
    <h1 style="color: green"> 
    GeeksforGeeks 
</h1>
    <h2>HTML Track srclang Attribute</h2>

    <video width="600" 
           height="400" 
           controls>

        <track src="CSS-animation-duration02.mp4" 
               id="myTrack1" 
               kind="subtitles"
               srclang="en" 
               label="English">

            <source id="myTrack"
                    src="CSS-animation-duration02.mp4"
                    type="video/mp4">
    </video>
</body>

</html>
```

**Output:**
![](img/a7892532f0cec82431711e296208d182.png)

**Supported Browsers:** The browsers supported by **<track> srclang Attribute** are listed below:

*   Google Chrome 18.0
*   Internet Explorer 10.0
*   Firefox 31.0
*   Apple Safari 6.0
*   Opera 15.0