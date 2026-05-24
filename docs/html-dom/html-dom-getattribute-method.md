# HTML DOM getAttribute()方法

> 原文:[https://www.geeksforgeeks.org/html-dom-getattribute-method/](https://www.geeksforgeeks.org/html-dom-getattribute-method/)

在本文中，我们将学习 **HTML DOM getAttribute()方法**，并通过示例了解它们的实现。

HTML DOM **getAttribute()** 方法用于获取元素的属性值。通过指定属性的名称，它可以获得该元素的值。要从非标准属性中获取值，我们可以使用 getAttribute()方法。

**语法:**

```html
Object.getAttribute(attributename)
```

**参数值:**

*   **属性名**:是字符串类型的必选参数，指定需要检索值的属性的名称。

**返回值:**返回元素上指定属性的值。如果指定的属性不存在，它将返回 null 或空字符串。

**示例 1:** 此示例说明了 DOM **getAttribute()** 方法，该方法为元素的指定名称指定属性值。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>DOM getAttribute() Method</title>
</head>

<body>
    <center>
        <h1 style="color:green;width:50%;">
            GeeksforGeeks
        </h1>
        <h2>DOM getAttribute() Method</h2>
        <br>
        <button id="button" onclick="geeks()">Submit</button>
        <p id="gfg"></p>

        <script>
        function geeks() {
            var rk =
            document.getElementById("button").getAttribute("onClick");
            document.getElementById("gfg").innerHTML = rk;
        }
        </script>
    </center>
</body>

</html>
```

**输出:**

![](img/6593a2a334d1bf8b58e307297fa7f7f0.png)

DOM getAttribute()方法

**示例 2:** 此示例说明了 DOM **getAttribute()** 方法来检索元素的 href 属性值。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>DOM getAttribute() Method</title>
</head>

<body>
    <center>
        <h1 style="color:green;width:50%;">
                GeeksforGeeks
            </h1>
        <h2>DOM getAttribute() Method</h2>
        <a id="gfg" href="www.geeksforgeeks.com">
          GeeksforGeeks
        </a>
        <br>
        <br>
        <button id="button" onclick="geeks()">Submit</button>
        <br>
        <p id="rk"></p>

        <script>
        function geeks() {
            var rk = document.getElementById("gfg").getAttribute("href");
            document.getElementById("rk").innerHTML = rk;
        }
        </script>
    </center>
</body>

</html>
```

**输出:**

![](img/d9a49af835ab3b583bf9a71d2334b72c.png)

DOM getAttribute()方法

**支持的浏览器:**下面列出了**DOM getAttribute()**T4 方法支持的浏览器:

*   谷歌 Chrome 1.0
*   Internet Explorer 5.0
*   微软边缘 12.0
*   Firefox 1.0
*   Opera 8.0
*   Safari 1.0