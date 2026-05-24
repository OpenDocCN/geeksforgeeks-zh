# HTML DOM 文档位置属性

> 原文:[https://www . geesforgeks . org/html-DOM-document-location-property/](https://www.geeksforgeeks.org/html-dom-document-location-property/)

**文档位置**属性返回文档的位置，该位置包含关于文档的网址的信息**。这是只读属性。**

**语法:**

```html
loc = document.location;
```

**返回值:**该属性返回文档的**字符串网址**位置。

**示例:**在本例中，我们将学习如何使用该属性获取文档位置 URL。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body>
    <h1>GeeksforGeeks</h1>

    <button onclick="get()">
        Get The URL
    </button>

    <script type="text/javascript">
        function get() {
            alert(document.location);
        }
    </script>
</body>

</html>
```

**输出:**

*   **点击按钮前:**

    ![](img/ebc5954a5a9b3245ab1b189633a8d467.png)

*   **点击按钮后:**

    ![](img/0aff9bd655eae1e753abe4027f0e6316.png)

**支持的浏览器:**

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队