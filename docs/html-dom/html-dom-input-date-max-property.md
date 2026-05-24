# HTML | DOM 输入日期最大属性

> 原文:[https://www . geesforgeks . org/html-DOM-input-date-max-property/](https://www.geeksforgeeks.org/html-dom-input-date-max-property/)

**输入日期最大值**属性用于设置或返回日期字段的最大属性值。max 属性返回一个表示允许的最大日期的字符串。
**语法:**

*   用于返回最大属性:

```html
inputdateObject.max
```

*   用于设置最大属性:

```html
inputdateObject.max = YYYY-MM-DD
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

**返回值:**返回一个代表日期字段最大值的字符串值。

下面的程序说明了最大日期属性:
**获取日期字段允许的最大日期。**T3】

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>Input Date max Property in HTML</title>
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
    <h2>Input Date max Property</h2>
    <br>

<p>The range of date accepted is between 2019-02-18 and 2019-02-20:
        <input type="date" id="Test_Date" min="2019-02-18" max="2019-02-20c

<p>to return the max range of the date field,
          double click the "Return Max" button.</p>

        <button ondblclick="My_Date()">Return Max</button>

        <p id="test"></p>

        <script>
            function My_Date() {
                var d = document.getElementById("Test_Date").max;
                document.getElementById("test").innerHTML = d;
            }
        </script>

</body>

</html>
```

**输出:**

![](img/3a6998b1e03f6694104061910519f546.png)

**点击**按钮后

![](img/43614cdb2355ee765d09089171c34d4c.png)

**示例-2:** 下面的代码设置了 date max 属性。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>Input Date max Property in HTML</title>
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
    <h2>Input Date max Property</h2>
        <input type="date"
               id="Test_Date"
               min="2019-02-18"
               max="2019-02-20"><br>

<p>to set the max range of the date field,
          double click the "Return Max" button.</p>

        <button ondblclick="My_Date()">Set Max</button>

        <p id="test"></p>

        <script>
            function My_Date() {
                var d = document.getElementById("Test_Date").max = "2020-12-12";
                document.getElementById("test").innerHTML = d;
            }
        </script>

</body>

</html>
```

**之前:**

![](img/1e7283e8d2cfb843927f8949c753cc27.png)

**之后:**

![](img/cd8547cf091ecd3d6ca0b2f24b1a9c9f.png)

**支持的网络浏览器:**

*   苹果 Safari
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   谷歌 Chrome
*   歌剧