# HTML | DOM 锚点原点属性

> 原文:[https://www . geesforgeks . org/html-DOM-anchor-origin-property/](https://www.geeksforgeeks.org/html-dom-anchor-origin-property/)

HTML DOM 中的**锚点原点属性**用于返回 href 属性值的协议、主机名和端口号。它是只读属性，返回一个表示协议、域名和网址端口号的字符串值。

**语法:**

```html
anchorObject.origin
```

下面的程序说明了锚源属性在超文本标记语言中的使用:

**示例:**本示例返回锚点原点属性。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML DOM Anchor origin Property
    </title>
</head>

<body>
    <center>
        <h1>
        GeeksForGeeks
    </h1>

        <h2>
        DOM Anchor origin Property
    </h2>

        <p>Welcome to
            <a href=
    "http://www.example.com:4097/test.htm#part2"
            id="GFG"
            rel="nofollow"
            target="_self"> 
                GeeksforGeeks 
            </a>
        </p>

        <button onclick="myGeeks()">
        Submit
    </button>

        <p id="sudo"
        style="color:green;
                font-size:25px;">
    </p>

        <script>
            function myGeeks() {

                var x =
                    document.getElementById(
                    "GFG").origin;

                document.getElementById(
                "sudo").innerHTML = x;
            }
        </script>
    </center>
</body>

</html>
```

**输出:**

**点击按钮前:**
![](img/7da60c8da1d1f6a0ad90ce894d7328c2.png)

**点击按钮后:**
![](img/a89f614e5155bde44c2c3d3ba825de5d.png)

**支持的浏览器:****DOM Anchor 原点属性**支持的浏览器如下:

*   谷歌 Chrome
*   Internet Explorer 10.0 +
*   火狐浏览器
*   歌剧
*   旅行队