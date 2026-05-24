# HTML | DOM 输入月份只读属性

> 原文:[https://www . geesforgeks . org/html-DOM-input-month-readonly-property/](https://www.geeksforgeeks.org/html-dom-input-month-readonly-property/)

HTML DOM 中的 **DOM 输入月只读**属性用于**设置**或**返回**输入月字段是否为只读*。
可以复制但不能修改。*

**语法:**

*   它返回 readOnly 属性。

    ```html
    monthObject.readOnly
    ```

*   它用于设置 readOnly 属性。

    ```html
    monthObject.readOnly = "true|false"
    ```

**属性值:**

*   **true:** 设置月字段的只读属性。
*   **false:** 为默认值。它定义了月份字段不是只读的。

**返回值:**返回一个布尔值，表示月份字段是否为只读。

**示例-1:** 本示例返回输入月份只读属性。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
     HTML DOM Input Month readOnly Property
    </title>
</head>

<body style="text-align:center;">

    <h1>GeeksForGeeks</h1>

    <h2>
      DOM Input Month readOnly Property
  </h2>
    <form id="myGeeks">
        <input type="month" 
               id="month_id" 
               name="geeks" 
               readOnly>
    </form>
    <br>
    <button onclick="myGeeks()">
      Click Here!
  </button>

    <p id="GFG" 
       style="font-size:20px;">
  </p>

    <!-- Script to return
      the readOnly property-->
    <script>
        function myGeeks() {

            var gfg = 
                document.getElementById(
                  "month_id").readOnly;

            document.getElementById(
              "GFG").innerHTML = gfg;
        }
    </script>
</body>

</html>
```

**输出**
**点击按钮前:**
![](img/a55ac195f7c7a2b58ccc648ef4de6258.png)

**点击按钮后:**
![](img/68a28a219bd5e4153977052ad79346c1.png)

**示例-2:** 本示例说明如何**设置或更改**只读属性。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML DOM Input Month readOnly Property
    </title>
</head>

<body style="text-align:center;">

    <h1>GeeksForGeeks</h1>

    <h2>DOM Input Month readOnly Property</h2>
    <form id="myGeeks">
        <input type="month" 
               id="month_id" 
               name="geeks" 
               readOnly>
    </form>
    <br>
    <button onclick="myGeeks()">
      Click Here!
  </button>

    <p id="GFG" 
       style="font-size:20px;">
  </p>

    <!-- Script to set the 
     readOnly Property-->
    <script>
        function myGeeks() {

            var gfg = 
                document.getElementById(
                  "month_id");
            gfg.readOnly = false;
            var g = gfg.readOnly;

            document.getElementById(
              "GFG").innerHTML = g;
        }
    </script>
</body>

</html>
```

**输出:**
**点击按钮前:**
![](img/1d634a6326cb9e9d38e5a6caa5ced633.png)

**点击按钮后:**
![](img/443e016a45bf06c54b37880cd100c74b.png)

**支持的浏览器:**T2 DOM 输入月份只读属性支持的浏览器如下:

*   谷歌 Chrome
*   Internet Explorer 10.0 +
*   火狐浏览器
*   歌剧
*   旅行队

**注意:**在 Firefox 中，输入 **type="month"** 元素不显示任何日期字段或日历。