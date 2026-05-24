# HTML | DOM 输入日期时间最大属性

> 原文:[https://www . geesforgeks . org/html-DOM-input-datetime-max-property/](https://www.geeksforgeeks.org/html-dom-input-datetime-max-property/)

**输入 Datetime max** 属性用于设置或返回 Datetime 字段的 max 属性值。
Input Datetime max 属性返回一个表示允许的最大日期和时间的字符串。
**语法:**

*   用于返回最大属性:

```html
datetimeObject.max
```

*   用于设置最大属性:

```html
datetimeObject.max = YYYY-MM-DDThh:mm:ssTZD
```

**房产价值:**

*   **YYYY-MM-DDThh:mm:ssTZD :** 用于指定允许的最大日期和时间。
    *   YYYY:指定年份。
    *   MM:指定月份。
    *   DD:它指定了一个月中的某一天。
    *   如果还输入了时间，它会指定分隔符。
    *   hh:它指定了小时。
    *   它指定了分钟。
    *   ss:它指定了秒数。
    *   TZD:它指定了时区指示器。

**返回值:**它返回一个字符串值，该值定义了日期时间字段的最大日期和时间。

下面的程序说明了 Datetime Max 属性:
**示例 1:** 获取 Datetime 字段允许的最大日期和时间。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>Input Datetime max Property in HTML</title>
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
    <h2>Input Datetime max Property</h2>
    <br>

<p>The range of date and time accepted is between
      2019-02-18 12:00 AM and 2019-02-20 12:00 AM:</p>

        <input type="datetime" id="Test_Datetime"
        min="2019-02-18T12:00Z" max="2019-02-20T12:00Z">

<p>To return the max range of the datetime field,
               double click the "Return Max" button.</p>

        <button ondblclick="My_Datetime()">Return Max</button>

        <p id="test"></p>

        <script>
            function My_Datetime() {
                var d = document.getElementById("Test_Datetime").max;
                document.getElementById("test").innerHTML = d;
            }
        </script>

</body>

</html>

```

**输出:**
**前:**

![](img/c340aaaec0b8604321d3f11982a318ab.png)

**点击**按钮后

![](img/0304663127a5807f0ef621e34a505e09.png)

**示例 2:** 设置日期时间最大值属性

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>Input Datetime max Property in HTML</title>
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
    <h2>Input Datetime max Property</h2>
    <br>

        <input type="datetime" id="Test_Datetime"
        min="2019-02-18T12:00Z" max="2019-02-20T12:00Z">

<p>To set the max range of the datetime field,
               double click the "Set Max" button.</p>

        <button ondblclick="My_Datetime()">Set Max</button>

        <p id="test"></p>

        <script>
            function My_Datetime() {
                var d = document.getElementById("Test_Datetime").max =
                    "2020-02-02";
                document.getElementById("test").innerHTML = d;
            }
        </script>

</body>

</html>

```

**输出:**

**之前:**

![](img/4438185b18d0418ae7a58a4ec9085cda.png)

**点击按钮**后

![](img/9a91910f5182fe573ab8d26693b10a3b.png)

2020-02-02

**支持的网络浏览器**

*   苹果 Safari
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   谷歌 Chrome
*   歌剧