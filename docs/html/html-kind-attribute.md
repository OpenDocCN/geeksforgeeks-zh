# HTML |种类属性

> 原文:[https://www.geeksforgeeks.org/html-kind-attribute/](https://www.geeksforgeeks.org/html-kind-attribute/)

**HTML 种类属性**用于指定轨迹的种类。此属性仅用于 **<轨迹>** 元素。

**语法:**

```html
<track src="subtitles_en.vtt" kind="subtitles" srclang="en">
```

**适用:**

*   <track>

**示例:**

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
    <h2>HTML Kind  Attribute</h2>

    <video width="100" height="100" controls>

        <track src=
"https://contribute.geeksforgeeks.org/wp-content/uploads/11.mp4" 
               id="myTrack" 
               kind="subtitles" 
               srclang="en" 
               label="English" 
               default>

            <source id="myTrack2" 
                    src=
"https://contribute.geeksforgeeks.org/wp-content/uploads/11.mp4"
                    type="video/mp4">

    </video>
</body>

</html>
```

**输出:**
![](img/c7e456741277e1712d9873f90364e851.png)

**支持的浏览器:****HTML 种类属性**支持的浏览器如下:

*   谷歌 Chrome 18.0
*   Internet Explorer 10.0
*   Firefox 31.0
*   苹果 Safari 6.0
*   Opera 15.0