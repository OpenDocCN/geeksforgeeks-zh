# HTML | DOM 输入时间最小值属性

> 原文:[https://www . geesforgeks . org/html-DOM-input-time-min-property/](https://www.geeksforgeeks.org/html-dom-input-time-min-property/)

**DOM 输入时间最小值属性**用于**设置**或**返回** *一个数字字段*的最小值属性。min 属性定义了输入时间字段的最短时间。

**语法:**

*   它返回 min 属性。

    ```html
    timeObject.min
    ```

*   它用于设置 min 属性。

    ```html
    timeObject.min = number
    ```

**属性值:**

*   **hh:mm:ss . ms–**用于指定时间字段允许的最短时间。
*   **hh-** 指定小时。
*   **mm-** 指定分钟。
*   **ss-** 指定秒。
*   **毫秒-** 它指定毫秒。

**返回值:**返回一个字符串值，代表时间字段允许的最短时间。

**示例-1:** 本示例说明如何返回输入时间最小值属性。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        DOM Input Time min Property
    </title>
</head>

<body>
    <center>
        <h1 style="color:green;"> 
                GeeksForGeeks 
            </h1>

        <h2>
          DOM Input Time min Property
      </h2>

        <label for="uname"
               style="color:green">
            <b>Enter time</b>
        </label>

        <input type="time" 
               id="gfg" 
               name="Geek_time" 
               placeholder="Enter time" 
               step="5" 
               min="16:00" 
               max="22:00">

        <br>
        <br>

        <button type="button"
                onclick="geeks()">
            Click
        </button>

        <p id="GFG" 
           style="font-size:24px;
                  color:green'">
      </p>

        <script>
            function geeks() {

                var link = 
                    document.getElementById(
                      "gfg").min;

                document.getElementById(
                  "GFG").innerHTML = link;
            }
        </script>
    </center>
</body>

</html>
```

**输出:**
**点击按钮前:**
![](img/a64531c0caed5e45d3568b7d93e535bd.png)

**点击按钮后:**
![](img/f70fa632a8936560031296b0596b349d.png)

**示例-2:** 本示例说明如何**设置**属性。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        DOM Input Time min Property
    </title>
</head>

<body>
    <center>
        <h1 style="color:green;"> 
                GeeksForGeeks 
            </h1>

        <h2>
          DOM Input Time min Property
      </h2>

        <label for="uname"
               style="color:green">
            <b>Enter time</b>
        </label>

        <input type="time"
               id="gfg"
               name="Geek_time" 
               placeholder="Enter time"
               step="5" 
               min="16:00" 
               max="22:00">

        <br>
        <br>

        <button type="button"
                onclick="geeks()">
            Click
        </button>

        <p id="GFG" 
           style="font-size:24px;
                  color:green'">
      </p>

        <script>
            function geeks() {

                var link = 
                    document.getElementById(
                      "gfg").min = "14:00";

                document.getElementById(
                  "GFG").innerHTML = 
                  "The value of the min attribute"+
                  " was changed to " + link;
            }
        </script>
    </center>
</body>

</html>
```

**输出:**
**点击按钮前:**
![](img/a64531c0caed5e45d3568b7d93e535bd.png)

**点击按钮后:**
![](img/e1b4a7453f0434b5c339134959bfe0a7.png)

**支持的浏览器:**以下列出的 **DOM 输入时间 min 属性**支持的浏览器:

*   谷歌 Chrome
*   Internet Explorer 10.0 +
*   火狐浏览器
*   歌剧
*   旅行队