# HTML | track default Attribute

> 原文：[https://www.geeksforgeeks.org/html-track-default-attribute/](https://www.geeksforgeeks.org/html-track-default-attribute/)

The **HTML <track> default Attribute** is a Boolean attribute. This attribute is used to specify that the track will be enabled if the user’s preferences do not indicate that another track would be more appropriate.

**Note:** With a default attribute, there must not be more than one track element per media element.

**Syntax:**

```html
<track src="subtitles_en.vtt" default>
```

**Below Example illustrates the use of default attribute in **<track>** element.**
**Example:**

```html
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
    <h2> 
    HTML <track>default Attribute 
</h2>

    <video width="100" 
           height="100" 
           controls>

        <track src=
"https://contribute.geeksforgeeks.org/wp-content/uploads/11.mp4" 
               kind="subtitles" 
               srclang="en"
               label="English" 
               default>

            <source id="myTrack" 
                    src=
"https://contribute.geeksforgeeks.org/wp-content/uploads/11.mp4" 
                    type="video/mp4">

    </video>
</body>

</html>
```

**Output:**
![](img/8f67bcaa64a346a04b48537afa102925.png)

**Supported Browsers:** The browsers supported by **HTML <track> default Attribute** are listed below:

*   Google Chrome 18.0
*   Internet Explorer 10.0
*   Firefox 31.0
*   Apple Safari 6.0
*   Opera 15.0