# HTML | DOM clientLeft 属性

> 原文:[https://www.geeksforgeeks.org/html-dom-clientleft-property/](https://www.geeksforgeeks.org/html-dom-clientleft-property/)

**DOM clientLeft** 属性用于以像素为单位返回元素左边框的宽度。它不包括左边距或左边距的宽度测量。它是只读属性。

**语法:**

```html
element.clientLeft 
```

**返回值:**返回一个代表元素左边框宽度的数值。

**示例:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML | DOM clientLeft Property

    </title>
    <style>
        h1 {
            color: green;
            font-size: 35px;
        }

        #GFG {
            height: 100px;
            width: 350px;
            padding: 20px;
            margin: 25px;
            border: 10px solid coral;
            background-color: green;
        }
    </style>
</head>

<body>
    <center>
        <h1>GeeksForGeeks</h1>
        <h2>DOM clientLeft Property </h2>

        <div id="GFG">
            <p style="color:white;font-size:25px;">
                GeeksforGeeks
            </p>
            <p id="sudo" style="color:white;"></p>
        </div>
        <button onclick="Geeks()">Submit</button>
        <script>
            function Geeks() {
                var w = document.getElementById("GFG");

                // Using clientTop property
                var x = "Border-Top-Width is: " 
                + w.clientTop + "px<br>";

                x += "Border-Left-width  : " 
                + w.clientLeft + "px";
                document.getElementById("sudo").innerHTML = x;
            }
        </script>
    </center>

</body>

</html>
```

**输出:**

*   **最初:**
    ![](img/8b88e6e5dba3449d0e4c6f331f94ae21.png)
*   **点击按钮后:**
    ![](img/6ea927dd6cbd8e0e599dda9dc88a62b2.png)

**支持的浏览器:**DOM client left 属性支持的浏览器如下:

*   谷歌 Chrome 1.0
*   Internet Explorer 4.0
*   Firefox 1.0
*   歌剧 3.5
*   Safari 1.0