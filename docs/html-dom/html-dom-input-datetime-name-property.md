# HTML | DOM 输入日期时间名称属性

> 原文:[https://www . geesforgeks . org/html-DOM-input-datetime-name-property/](https://www.geeksforgeeks.org/html-dom-input-datetime-name-property/)

输入日期时间名称属性用于设置或返回日期时间字段的名称属性值。
已经提交给服务器的表单数据可以通过名称属性来识别。name 属性还用于在客户端使用 Javascript 引用表单数据。

**语法:**

*   要返回 name 属性，请执行以下操作:

```html
datetimeObject.name
```

*   要设置 name 属性，请执行以下操作:

```html
datetimeObject.name
```

**属性值:**

*   **名称:**用于指定日期时间字段的名称。

**返回值:**返回指定输入日期时间字段名称的字符串值。

下面的程序说明了日期时间名称属性:
**示例 1:** 获取日期时间字段的名称。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>Input Datetime name Property in HTML</title>
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
    <h2>Input Datetime name Property</h2>
    <br> Date of Birth:
    <input type="datetime" id="Test_Datetime" name="DOB">

<p>To display the value of the name attribute of the datetime
      field, double-click the "Return Name" button.</p>

    <button ondblclick="My_Datetime()">Return Name</button>

    <p id="test"></p>

    <script>
        function My_Datetime() {
            var n = document.getElementById("Test_Datetime").name;
            document.getElementById("test").innerHTML = n;
        }
    </script>

</body>

</html>

```

**输出:**
**前:**

![](img/cfdf44a7018cb8efa508f57553cb9a03.png)

**点击按钮后:**

![](img/cfbc10dc597039dcfc1acd87da8e7dc9.png)

**示例 2:** 下面的代码设置日期名称属性。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>Input Datetime name Property in HTML</title>
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
    <h2>Input Datetime name Property</h2>
    <br> Date of Birth:
    <input type="datetime" id="Test_Datetime" name="DOB">

<p>To Set the value of the name attribute of the datetime
      field, double-click the "Return Name" button.</p>

    <button ondblclick="My_Datetime()">Set Name</button>

    <p id="test"></p>

    <script>
        function My_Datetime() {
            var n = document.getElementById("Test_Datetime").name =
                "date of birth";
            document.getElementById("test").innerHTML = n;
        }
    </script>

</body>

</html>

```

**输出:**

**之前:**

![](img/5f4a19783f6f429c143820921c13920f.png)

**点击按钮后:**

![](img/de56091a91dec295c2406242d1ce9f72.png)

**支持的网络浏览器**

*   苹果 Safari
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   谷歌 Chrome
*   歌剧