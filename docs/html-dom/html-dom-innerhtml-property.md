# HTML DOM innerHTML 属性

> 原文:[https://www.geeksforgeeks.org/html-dom-innerhtml-property/](https://www.geeksforgeeks.org/html-dom-innerhtml-property/)

DOM **innerHTML** 属性用于设置或返回元素的 HTML 内容。

**语法:**

它返回内部 HTML 属性。

```html
Object.innerHTML
```

它用于设置 innerHTML 属性。

```html
Object.innerHTML = value
```

哪里，

*   **值:**它代表 HTML 元素的文本内容。

**返回值:**这个属性返回一个代表元素 HTML 内容的字符串。

**示例 1:** 此示例显示了如何使用 innerHTML 属性更改段落标记的内容。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body style="text-align: center">
    <h1 style="color:green">
        GeeksforGeeks
    </h1>
    <h2>
        DOM innerHTML Property
    </h2>
    <p id="p">GeeksforGeeks</p>

    <button onclick="geek()">Click me!</button>
    <script>
    function geek() {
        document.getElementById("p").innerHTML =
        "A computer science portal for geeks.";
    }
    </script>
</body>

</html>
```

**输出:**

![](img/6b281d3a9290118f453e8ba78c254707.png)

内部 HTML 属性

**示例 2:** 这个示例展示了如何使用 innerHTML 属性获取段落标记的值。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body style="text-align: center">
    <h1 style="color:green">
        GeeksforGeeks
    </h1>
    <h2>
        DOM innerHTML Property
    </h2>
    <p id="P">A computer science portal for geeks.</p>

    <button onclick="geek()">Try it</button>
    <p id="p"></p>

    <script>
    function geek() {
        var x = document.getElementById("P").innerHTML;
        document.getElementById("p").innerHTML = x;
        document.getElementById("p").style.color = "green";
    }
    </script>
</body>

</html>
```

**输出:**

![](img/7d78ad9b3333baca632d848e498498ac.png)

内部 HTML 属性

**支持的浏览器:**DOM**innerHTML**属性支持的浏览器如下:

*   谷歌 Chrome 1.0
*   Internet Explorer 5.5
*   微软边缘 12.0
*   Firefox 45.0
*   歌剧 9.6
*   Safari 3.0