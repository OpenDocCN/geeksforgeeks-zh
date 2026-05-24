# HTML | DOM 锚点主机名属性

> 原文:[https://www . geesforgeks . org/html-DOM-anchor-hostname-property/](https://www.geeksforgeeks.org/html-dom-anchor-hostname-property/)

HTML DOM 中的 **DOM 锚点主机名属性**用于**设置**或**返回***href 属性值的主机名部分*。

**语法:**

*   它返回主机名属性。

    ```html
    anchorObject.hostname
    ```

*   用于设置主机名属性:

    ```html
    anchorObject.hostname = hostname
    ```

**属性值:**它包含指定网址主机名的值，即**主机名**。

**返回值:**返回代表网址域名或 IP 地址的字符串值。

**示例-1:** 本示例返回主机名属性。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML DOM Anchor hostname Property
    </title>
</head>

<body>
    <center>
        <h1>
          GeeksForGeeks
      </h1>

        <h2>
          DOM Anchor hostname Property
      </h2>

        <p>Welcome to
            <a href=
      "http://www.example.com:4097/test.htm#part2" 
               id="GFG" 
               rel="nofollow"
               hreflang="en-us" 
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
                    document.getElementById("GFG").hostname

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
![](img/55a5a69268d2506a2dd54f3239d89bc5.png)

**点击按钮后:**
![](img/72b4597e6940c0d7656d82c631d163f5.png)

**示例-2:** 本示例设置主机名属性。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML DOM Anchor hostname Property
    </title>
</head>

<body>
    <center>
        <h1>
          GeeksForGeeks
      </h1>

        <h2>
          DOM Anchor hostname Property
      </h2>

        <p>Welcome to
            <a href=
       "http://www.example.com:4097/test.htm#part2" 
               id="GFG"
               rel="nofollow"
               hreflang="en-us"
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
                      "GFG").hostname = 
                    "www.GeeksForGeeks.org"

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
![](img/b39aee1910ba8006f0d2cf08d9f4a531.png)
**点击按钮后:**
![](img/55a5a69268d2506a2dd54f3239d89bc5.png)

**支持的浏览器:****DOM Anchor 主机名属性**支持的浏览器如下:

*   谷歌 Chrome
*   Internet Explorer 10.0 +
*   火狐浏览器
*   歌剧
*   旅行队