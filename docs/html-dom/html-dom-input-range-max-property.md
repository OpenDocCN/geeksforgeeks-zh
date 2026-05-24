# HTML | DOM 输入范围最大属性

> 原文:[https://www . geesforgeks . org/html-DOM-input-range-max-property/](https://www.geeksforgeeks.org/html-dom-input-range-max-property/)

HTML DOM 中的**输入范围最大属性**用于**设置**或**返回** *滑块控件*的最大属性值。max 属性用于指定滑块控件的最大值。

**语法:**

*   **返回输入范围最大属性:**

    ```html
    rangeObject.max
    ```

*   **用于设置输入范围最大属性:**

    ```html
    rangeObject.max = number
    ```

**属性值:**它包含单个值**数字**，指定滑块控件允许的最大值。

**返回值:**返回一个代表最大允许值的字符串。

**示例-1:** 返回输入范围最大属性

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        DOM Input Range max Property
    </title>
</head>

<body style="text-align:center;">

    <h1 style="color:green;"> 
            GeeksForGeeks 
        </h1>

    <h2>DOM Input Range max Property</h2>

    <input type="range" 
           id="myRange" 
           min="10" 
           max="50">

    <br>
    <br>

    <button onclick="myGeeks()">
        Click Here!
    </button>

    <p id="GFG"
       style="font-size:23px;
              color:green;">
  </p>

    <script>
        function myGeeks() {

            // Accessing input value 
            var x =
                document.getElementById(
                  "myRange").max;

            document.getElementById(
              "GFG").innerHTML = x;
        }
    </script>

</body>

</html>
```

**输出:**
**之前点击按钮:**
![](img/a261973e6393d5752a742f46dbddf8b3.png)

**点击按钮后:**
![](img/871c591d932cf5ab5b67ec1e73d05065.png)

**示例-2:** 设置输入范围最大属性。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        DOM Input Range max Property
    </title>
</head>

<body style="text-align:center;">

    <h1 style="color:green;"> 
            GeeksForGeeks 
        </h1>

    <h2>
      DOM Input Range max Property
  </h2>

    <input type="range" 
           id="myRange" 
           min="10"
           max="50">

    <br>
    <br>

    <button onclick="myGeeks()">
        Click Here!
    </button>

    <p id="GFG" 
       style="font-size:23px;
              color:green;">
  </p>

    <script>
        function myGeeks() {

            // Accessing input value  
            var x =
                document.getElementById(
                  "myRange").max = "70";

            document.getElementById(
              "GFG").innerHTML =
                "The value of the max attribute"+
              " was changed to " + x;
        }
    </script>

</body>

</html>
```

**输出:**
**点击按钮前:**
![](img/a261973e6393d5752a742f46dbddf8b3.png)
**点击按钮后:**
![](img/93e84091e0ac4e4bd947a6966b2c77ca.png)

**支持的浏览器:****DOM 输入范围最大属性**支持的浏览器如下:

*   谷歌 Chrome
*   Internet Explorer 10.0
*   火狐浏览器
*   旅行队
*   歌剧