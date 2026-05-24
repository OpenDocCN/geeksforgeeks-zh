# HTML | DOM 锚点下载属性

> 原文:[https://www . geesforgeks . org/html-DOM-anchor-download-property/](https://www.geeksforgeeks.org/html-dom-anchor-download-property/)

HTML DOM 中的 **DOM 锚点下载属性**用于**设置**或**返回** *一个链接的下载属性值*。**下载属性**用于指定用户点击时要下载的目标链接。

**语法:**

*   它返回下载属性。

    ```html
    anchorObject.download
    ```

*   它用于设置下载属性。

    ```html
    anchorObject.download = filename
    ```

**属性值:**

*   **文件名:**指定需要下载的文件的名称。

**返回值:**返回一个代表下载文件名称的字符串值。

**示例-1:** 本示例返回下载属性。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML DOM Anchor download Property
    </title>
</head>

<body>
    <center>
        <h1>GeeksForGeeks</h1>

        <h2>
          DOM Anchor download Property
      </h2>

        <a href=
    "http://www.example.com:4097/test.htm#part2" 
           id="GFG"
           rel="nofollow" 
           hreflang="en-us"
           target="_self" 
           download="GFG_Logo">

            <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/gfg1-11.png" 
                 width="300" 
                 height="250">
        </a>

        <BR>
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
                      "GFG").download;

                document.getElementById(
                  "sudo").innerHTML = x;
            }
        </script> "
    </center>
</body>

</html>
```

**输出:**

**点击按钮前:**
![](img/149eccb2a12c0a800895bc6d066b8331.png)
**点击按钮后:**
![](img/7bfef2a0ac51b215dd16c811ea3b60f7.png)

**示例-2 :** 本示例设置下载属性。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML DOM Anchor download Property
    </title>
</head>

<body>
    <center>
        <h1>GeeksForGeeks</h1>

        <h2>
          DOM Anchor download Property
      </h2>

        <a href=
  "http://www.example.com:4097/test.htm#part2" 
           id="GFG"
           rel="nofollow"
           hreflang="en-us" 
           target="_self" 
           download="GFG_Logo">

            <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/gfg1-11.png" 
                 width="300" 
                 height="250">
        </a>

        <BR>
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
                      "GFG").download = "LOGO OF Geeks";

                document.getElementById(
                  "sudo").innerHTML = 
                  "The value of the download attribute "+
                  "was changed to " + x;
            }
        </script> "
    </center>
</body>

</html>
```

**输出:**
**点击
按钮前:**
![](img/149eccb2a12c0a800895bc6d066b8331.png)

**点击按钮后:**
![](img/2daeb47933850f48d3195e054f66ed48.png)

**支持的浏览器:****DOM Anchor 下载属性**支持的浏览器如下:

*   谷歌 Chrome
*   Internet Explorer 10.0 +
*   火狐浏览器
*   歌剧
*   旅行队