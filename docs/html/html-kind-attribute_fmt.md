
# HTML | Kind Attribute

> 原文: [https://www.geeksforgeeks.org/html-kind-attribute/](https://www.geeksforgeeks.org/html-kind-attribute/)

**HTML Kind Attribute** is used to specify the kind of the track. This attribute is only used for the **<track>** element.

**Syntax:**

```html
<track src="subtitles_en.vtt" kind="subtitles" srclang="en">
```

**Applicable:**

*   `<track>`

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
    <h2>HTML Kind Attribute</h2>

<video width="100" height="100" controls>

<track src="https://contribute.geeksforgeeks.org/wp-content/uploads/11.mp4" 
       id="myTrack" 
       kind="subtitles" 
       srclang="en" 
       label="English" 
       default>

<source id="myTrack2" 
          src="https://contribute.geeksforgeeks.org/wp-content/uploads/11.mp4" 
          type="video/mp4">

</video>
</body>

</html>
```

**Output:**
![Output Image](img/c7e456741277e1712d9873f90364e851.png)

**Supported Browsers:**

*   Google Chrome 18.0
*   Internet Explorer 10.0
*   Firefox 31.0
*   Apple Safari 6.0
*   Opera 15.0
