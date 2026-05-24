# HTML | DOM 样式寡妇属性

> 原文:[https://www . geesforgeks . org/html-DOM-style-windows-property/](https://www.geeksforgeeks.org/html-dom-style-widows-property/)

寡妇属性用于设置或返回最小行数。这些行必须在元素的页面顶部可见。寡妇属性仅影响块级元素。

**语法:**

*   **归还寡妇财产:**

    ```html
    object.style.widows
    ```

*   **设置寡妇属性:**

    ```html
    object.style.widows = "number | initial | inherit" 
    ```

**属性值:**

*   **数字:**指定最小可见行数的整数值。默认值为 2。
*   **初始值:**将该属性设置为默认值。
*   **inherit:** 从其父元素继承该属性。

**返回值:**返回一个字符串值，代表页面顶部要打印的最小行数。

**示例:**

```html
<html>

<head>
    <script>
        function CWidows() {
            document.getElementById("pID").style.widows
              = document.getElementById("widows").value;
        }
    </script>

    <style>
        .content {
            width: 400px;
            border-top: 19cm solid green;
        }

        @page {
            /* set size of printed page */
            size: 21cm 27cm;
            margin-top: 2cm;
        }

        @media print {
            .widows {
                widows: 2;
            }
        }
    </style>
</head>

<body>
    <center>
        <div class="content">
            <input id="widows" value="2">
            <button onclick="CWidows();">Change widows</button>
            <p style="font-size:120%" id="pID">
                Change widows and see the print preview.
                <br> Line 2
                <br> Line 3
                <br> Line 4
                <br> Line 5
                <br> Line 6
                <br> Line 7
                <br> Line 8
                <br>
            </p>
        <div class="content">
    </center>
</body>

</html>
```

**输出:**打印视图。
T3】

**支持的浏览器:****HTML DOM Style 寡妇属性**支持的浏览器如下:

*   谷歌 Chrome
*   歌剧