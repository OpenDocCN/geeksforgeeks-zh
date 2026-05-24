# HTML | DOM 输入时间名称属性

> 原文:[https://www . geesforgeks . org/html-DOM-input-time-name-property/](https://www.geeksforgeeks.org/html-dom-input-time-name-property/)

HTML DOM 中的 **DOM 输入时间名称属性**用于**设置**或**返回** *一个时间字段的名称属性值*。每个输入字段都需要名称属性。如果没有在输入字段中指定 name 属性，则根本不会发送该字段的数据。

**语法:**

*   它返回输入时间名称属性。

    ```html
    timeObject.name
    ```

*   它用于设置输入时间名称属性。

    ```html
    timeObject.name = name
    ```

**属性值:**它包含一个定义时间字段名称的值名。

**返回值:**返回代表时间字段名称的字符串值。

**示例-1:** 本示例说明如何返回输入时间名称属性。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        DOM Input Time name Property
    </title>
</head>

<body>
    <center>
        <h1 style="color:green;"> 
                GeeksForGeeks 
            </h1>

        <h2>
          DOM Input Time name Property
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
               readonly>

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
                      "gfg").name;

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
![](img/d7580d91d27b121faa6065d50f6db12d.png)

**点击按钮后:**
![](img/09be037dc3fafb17cd6a3c083e162614.png)

**示例-2:** 本示例说明如何**设置**属性。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        DOM Input Time name Property
    </title>
</head>

<body>
    <center>
        <h1 style="color:green;"> 
                GeeksForGeeks 
            </h1>

        <h2>
          DOM Input Time name Property
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
               readonly>

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
                      "gfg").name = "Hello Geeks";

                document.getElementById(
                  "GFG").innerHTML = 
                  "The value of the name attribute"+
                  " was changed to " + link;
            }
        </script>
    </center>
</body>

</html>
```

**输出:**
**点击按钮前:**
![](img/d7580d91d27b121faa6065d50f6db12d.png)

**点击按钮后:**
![](img/8f800c7e06602ffa3374395752ffeaf3.png)

**支持的浏览器:**以下列出的 **DOM 输入时间名称属性**支持的浏览器:

*   谷歌 Chrome
*   Internet Explorer 10.0 +
*   火狐浏览器
*   歌剧
*   旅行队