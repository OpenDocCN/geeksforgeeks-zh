# HTML |屏幕高度属性

> 原文:[https://www.geeksforgeeks.org/html-screen-height-property/](https://www.geeksforgeeks.org/html-screen-height-property/)

**屏幕高度**属性用于返回用户屏幕的总高度。它以像素为单位返回屏幕的总高度。
**语法:**

```html
screen.height
```

**返回值:**代表用户屏幕总高度的数字，以像素为单位

下面的程序说明了屏幕高度属性:
**检查用户屏幕的总高度。**T3】

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
      Screen height Property in HTML
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
    <h2>Screen height Property</h2>

<p>
      For checking the screen's total height,
      double click the "Check Height" button:
    </p>

    <button ondblclick="check_height()">
      Check Height
    </button>

    <p id="height"></p>

    <script>
        function check_height() {
            var h =
                "Total Screen Height In Pixels : "
                                + screen.height;
            document.getElementById("height").innerHTML = h;
        }
    </script>

</body>

</html>

```

**输出:**

![](img/f5feb67f354f65358be7df1b79b5fb02.png)

**点击**按钮后

![](img/803e7fe91169071f8995893d052e9d5d.png)

**支持的浏览器:**支持的浏览器*屏幕高度*如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队