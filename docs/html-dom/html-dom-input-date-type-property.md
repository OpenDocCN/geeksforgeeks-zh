# HTML | DOM 输入日期类型属性

> 原文:[https://www . geesforgeks . org/html-DOM-input-date-type-property/](https://www.geeksforgeeks.org/html-dom-input-date-type-property/)

输入日期类型属性用于返回日期字段的表单元素类型。输入日期类型属性返回一个字符串，该字符串表示日期字段的表单元素类型。

**语法:**

```html
inputdateObject.type
```

**返回值**:返回一个字符串值，代表日期字段的表单元素类型。

下面的程序说明了日期类型属性:
**返回日期字段的表单元素类型。**T3】

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>Input Date type Property in HTML</title>
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
    <h2>Input Date type Property</h2>
    <br> Date Of Birth:
    <input type="date" id="Test_Date">

<p>To find out the type of form element the date field is,
      double-click the "Check Type" button.</p>

    <button ondblclick="My_Date()">Check Type</button>

    <p id="test"></p>

    <script>
        function My_Date() {
            ").type;
            document.getElementById("test").innerHTML = t;
        }
    </script>

</body>

</html>

```

**输出:**
**点击按钮前:**

![](img/de97758a623be454bd9aa13667673d4c.png)

**双击按钮后:**

![](img/99cd987f6fb0614d6f7a18f8cfc57787.png)

**支持的网络浏览器:**

*   苹果 Safari
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   谷歌 Chrome
*   歌剧