# HTML | DOM clientTop 属性

> 原文:[https://www.geeksforgeeks.org/html-dom-clienttop-property/](https://www.geeksforgeeks.org/html-dom-clienttop-property/)

**DOM clientTop** 属性用于以像素为单位返回元素上边框的宽度。它不包括顶部填充或左边距的宽度测量。它是只读属性。

**语法:**

```html
element.clientTop 
```

**返回值:**返回一个代表元素上边框宽度的数值。

**示例:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML | DOM clientTop Property
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
            border-left: 10px solid coral;
            border-top: 15px solid blue;
            background-color: green;
        }
    </style>
</head>

<body>
    <center>
        <h1>GeeksForGeeks</h1>
        <h2>DOM clientTop Property </h2>

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

                x += "Border-Left-width : " 
                + w.clientLeft + "px";
                document.getElementById("sudo").innerHTML = x;
            }
        </script>

</body>

</html>
```

**输出:**

*   **最初:**
    ![](img/e0a702a98e5f981f4337d409201b9fa5.png)
*   **点击按钮后:**
    ![](img/7af2a82ad1134578473cbe412393d988.png)

**支持的浏览器:**T2 DOM client top 属性支持的浏览器如下:

*   谷歌 Chrome 1.0
*   Internet Explorer 4.0
*   Firefox 1.0
*   歌剧 3.5
*   Safari 1.0