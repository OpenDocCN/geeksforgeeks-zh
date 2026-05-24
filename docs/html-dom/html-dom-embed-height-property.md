# HTML | DOM 嵌入高度属性

> 原文:[https://www . geesforgeks . org/html-DOM-embed-height-property/](https://www.geeksforgeeks.org/html-dom-embed-height-property/)

HTML DOM 中的**嵌入高度属性**用于设置或返回高度属性的值。高度属性以像素为单位定义嵌入内容的高度。

**语法:**

*   **返回高度属性:**

    ```html
    embedObj.height
    ```

*   **设置高度属性:**

    ```html
    embedObj.height = pixels
    ```

**属性值:**

*   **px:** 以像素为单位指定嵌入内容的高度。

**返回值:**返回一个数字，表示嵌入内容的高度。

**示例:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML DOM Embed height Property
    </title>
</head>

<body>
    <center>
        <h1 style="color:green"> 
            GeeksforGeeks 
        </h1>

        <embed id="embedID" height="400"
            src="https://ide.geeksforgeeks.org">
        <br>

        <button onclick="GFGfun()">
            Try it
        </button>

        <p id="pid"></p>

        <script>
            function GFGfun() {
                var idheight = 
                document.getElementById("embedID").height;

                document.getElementById("pid").innerHTML
                        = idheight;
            }
        </script>
    </center>
</body>

</html>
```

**输出:**
**点击按钮前:**
![](img/1ad39ba9af54f7d1737090fc7f187d0b.png)
**点击按钮后:**
![](img/84e9b3c2cc55aa3a573a512b67e47c2f.png)

**示例:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML DOM Embed height Property
    </title>
</head>

<body>
    <center>
        <h1 style="color:green"> 
            GeeksforGeeks 
        </h1>

        <embed id="embedID"
            src="https://ide.geeksforgeeks.org">
        <br>

        <button onclick="GFGfun()">
            Try it
        </button>

        <p id="pid"></p>

        <script>
            function GFGfun() {
                var idheight = 
                document.getElementById("embedID").height
                        = 400;

                document.getElementById("pid").innerHTML
                        = idheight;
            }
        </script>
    </center>
</body>

</html>
```

**输出:**

*   **点击按钮前:**
    ![](img/cfe38b7b3c7528299b810d551c5251ef.png)
*   **点击按钮后:**
    ![](img/84e9b3c2cc55aa3a573a512b67e47c2f.png)

**支持的浏览器:****DOM 嵌入高度属性**支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   苹果 Safari
*   歌剧