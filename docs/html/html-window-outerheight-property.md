# HTML |窗口外部高度属性

> 原文:[https://www . geesforgeks . org/html-window-outer height-property/](https://www.geeksforgeeks.org/html-window-outerheight-property/)

**窗口外部高度属性**用于返回浏览器窗口的外部高度。它包括所有的界面元素，如工具栏、滚动条等。它是一个只读属性，返回一个代表浏览器窗口高度的数字(以像素为单位)。

**语法:**

```html
window.outerHeight
```

下面的程序说明了窗口外部高度属性:

**获取浏览器窗口的高度。**

```html
<!DOCTYPE html>
<html>

<head>
    <title>
      Window outerHeight Property in HTML
    </title>
    <style>
        h1 {
            color: green;
        }

        h2 {
            font-family: Impact;
        }

        body {
            text-align: center;
        }
    </style>
</head>

<body>

    <h1>GeeksforGeeks</h1>
    <h2>Window outerHeight Property</h2>

    <p>
      For returning the browser window's height,
      double click the "Check Height" button:
    </p>

    <button ondblclick="pixel()">
      Check Height
    </button>

    <p id="outerheight"></p>

    <script>
        function pixel() {
            var height = window.outerHeight;
            document.getElementById("outerheight").innerHTML =
                              "Height : " + height;
        }
    </script>

</body>

</html>
```

**输出:**
![](img/362d9bd013ee68abe705efbaa55c06fb.png)

**点击**
![](img/bcbd725514b3e5f01958adf89f6adc18.png)按钮后

**支持的浏览器:***窗口外高属性*支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队