# HTML | DOM 样式划片属性

> 原文:[https://www . geesforgeks . org/html-DOM-style-padding top-property/](https://www.geeksforgeeks.org/html-dom-style-paddingtop-property/)

样式填充属性用于设置或返回元素的顶部填充。
padding 属性在元素的边框内插入用户想要的空间。

**语法:**

*   获取属性:

    ```html
    object.style.paddingTop
    ```

*   设置属性:

    ```html
    object.style.paddingTop = "%|length|initial|inherit"
    ```

**返回值:**它返回一个字符串值，代表元素的顶部填充

**属性值:**

*   **% :** 用于定义以父元素宽度的%为单位的顶部填充。
*   **长度:**用于以长度单位定义顶部填充。
*   **初始值:**用于将该属性设置为默认值。
*   **inherit :** 用于从其父元素继承该属性。

下面的程序说明了样式填充属性方法:

**示例:设置< div >元素的顶部填充。**

```html
<!DOCTYPE html>
<html>

<head>
    <title>Style paddingTop in HTML</title>
    <style>
        #MyElement {
            border: 1px solid black;
            background-color: green;
            width: 300px;
            height: 300px;
        }

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
    <h2>Style paddingTop</h2>

    <p>For setting the top padding,
      double click the "Apply Top Padding" button: </p>
    <br>

    <button ondblclick="padding()">Apply Top Padding</button>

    <div id="MyElement">
        Geeksforgeeks is a portal for geeks.
    </div>

    <script>
        function padding() {
            document.getElementById("MyElement")
            .style.paddingTop = "100px";
        }
    </script>

</body>

</html>
```

**输出:**

*   Before Clicking the button:

    ![](img/503ae0aa44d0bdaea58b4711d5327de3.png)

*   点击按钮后:
    ![](img/873db1e878eab06e6814eb80a2679060.png)

**支持的浏览器:**以下是*HTML | DOM Style padding top Property*支持的浏览器:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   苹果 Safari