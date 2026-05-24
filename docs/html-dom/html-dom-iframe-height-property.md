# HTML | DOM IFrame 高度属性

> 原文:[https://www . geesforgeks . org/html-DOM-iframe-height-property/](https://www.geeksforgeeks.org/html-dom-iframe-height-property/)

**HTML DOM IFrame 高度属性**用于设置或返回 IFrame 元素的高度属性值。**高度属性**用于指定一个 Iframe 元素的高度。
**语法:**

*   它返回高度属性。

```html
iframeObject.height
```

*   它用于设置高度属性。

```html
iframeObject.height = pixels
```

**房产价值:**

*   **像素:**以像素为单位指定 Iframe 元素的高度

**返回值**返回一个字符串值，以像素为单位表示 Iframe 的高度。
**示例-1:** 本示例说明如何返回 Iframe 高度属性。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML DOM iframe height Property
    </title>
</head>

<body style="text-align:center;">

    <h1>GeeksforGeeks</h1>

    <h2>HTML DOM iframe height Property</h2>

    <iframe src=
"https://ide.geeksforgeeks.org/index.php"
            id="GFG"
            height="200"
            width="400">
  </iframe>
    <br>
    <br>
    <button onclick="Geeks()">Submit</button>
    <p id="sudo" style="font-size:20px"></p>

    <script>
        function Geeks() {
            var x =
                document.getElementById("GFG").height;
            document.getElementById("sudo").innerHTML = x;

        }
    </script>

</body>

</html>
```

**输出:**
**点击按钮前:**

![](img/decb8186973083846b828ae92d8c331c.png)

**点击按钮后:**

![](img/af72e9f5001185564f96d7e04462482d.png)

**示例-2:** 本示例说明如何设置 Iframe 高度属性。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML DOM iframe height Property
    </title>
</head>

<body style="text-align:center;">

    <h1>GeeksforGeeks</h1>

    <h2>HTML DOM iframe height Property</h2>

    <iframe src=
"https://ide.geeksforgeeks.org/index.php"
            id="GFG"
            height="200"
            width="400">
  </iframe>
    <br>
    <br>
    <button onclick="Geeks()">Submit</button>
    <p id="sudo" style="font-size:20px"></p>

    <script>
        function Geeks() {
            var x =
                document.getElementById("GFG").height =
                "400";
            document.getElementById("sudo").innerHTML = x;

        }
    </script>

</body>

</html>
```

**输出:**
**点击按钮前:**

![](img/1bc2819c0f7c79db870dac0a939f3286.png)

**点击按钮后:**

![](img/463f2aead0d87a6b0bc73148c6dc09ed.png)

**支持的浏览器:****HTML DOM IFrame 高度属性**支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   苹果 Safari
*   歌剧