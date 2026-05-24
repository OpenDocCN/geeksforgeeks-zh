# HTML | DOM 输入月份默认值属性

> 原文:[https://www . geesforgeks . org/html-DOM-input-month-default value-property/](https://www.geeksforgeeks.org/html-dom-input-month-defaultvalue-property/)

HTML DOM 中的 **DOM 输入月默认值**属性用于**设置**或**返回** **月字段的默认值**。它是在 value 属性中指定的值。

**语法:**

*   它返回 defaultValue 属性。

    ```html
    monthObject.defaultValue
    ```

*   它用于设置 defaultValue 属性。

    ```html
    monthObject.defaultValue = value
    ```

**属性值:**

*   **值:**指定月字段的默认值。

**返回值:**以字符串形式返回月字段的值。

**示例-1:** 本示例返回输入月份属性的默认值。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML DOM Input Month defaultValue Property
    </title>
</head>

<body style="text-align:center;">

    <h1>GeeksForGeeks</h1>

    <h2>
      DOM Input Month defaultValue Property
  </h2>
    <form id="myGeeks">
        <input type="month" 
               id="month_id"
               name="geeks"
               value="2019-10">
    </form>
    <br>
    <button onclick="myGeeks()">
      Click Here!
  </button>

    <p id="GFG" 
       style="font-size:20px;">
  </p>

    <!-- Script to return
     the  defaultValue-->
    <script>
        function myGeeks() {

            var gfg = 
                document.getElementById(
                  "month_id").defaultValue;

            document.getElementById(
              "GFG").innerHTML = gfg;
        }
    </script>
</body>

</html>
```

**输出**
**点击按钮前:**
![](img/85054302804c073eee3206d4e9d44fb1.png)

**点击按钮后:**
![](img/2f53158aa09ca974dbdcdf4c8d90c620.png)

**示例-2:** 本示例说明如何**设置或更改**默认值。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML DOM Input Month defaultValue Property
    </title>
</head>

<body style="text-align:center;">

    <h1>GeeksForGeeks</h1>

    <h2>
      DOM Input Month defaultValue Property
  </h2>
    <form id="myGeeks">
        <input type="month"
               id="month_id"
               name="geeks" 
               value="2019-10">
    </form>
    <br>
    <button onclick="myGeeks()">
      Click Here!
  </button>

    <p id="GFG" 
       style="font-size:20px;">
  </p>

    <!-- Script to set the 
    defaultValue of Month field-->
    <script>
        function myGeeks() {

            var gfg =
                document.getElementById(
                  "month_id");
            gfg.defaultValue = "2019-01";
            var g = gfg.defaultValue;

            document.getElementById(
              "GFG").innerHTML = g;
        }
    </script>
</body>

</html>
```

**输出:**
**点击按钮前:**
![](img/b1ba753e59ab308021f0d518d492e00c.png)

**点击按钮后:**
![](img/7660ebf8f5ee5a269f6d562a70bd66ea.png)

**支持的浏览器:**T2 DOM 输入月默认值属性支持的浏览器如下:

*   谷歌 Chrome
*   Internet Explorer 10.0 +
*   火狐浏览器
*   歌剧
*   旅行队

**注意:**在 Firefox 中，输入 **type="month"** 元素不显示任何日期字段或日历。