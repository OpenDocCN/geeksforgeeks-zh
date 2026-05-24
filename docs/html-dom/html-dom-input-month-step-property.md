# HTML | DOM 输入月步属性

> 原文:[https://www . geesforgeks . org/html-DOM-input-month-step-property/](https://www.geeksforgeeks.org/html-dom-input-month-step-property/)

**DOM 输入月步属性**用于**设置**或**返回** *月字段*步属性的值。HTML 中的 step 属性用于设置元素的离散步长。月份输入的默认步进值为 1。步长属性可以与最小值和最大值属性一起使用来创建合法值。

**语法:**

*   它返回 step 属性。

    ```html
    monthObject.step
    ```

*   它用于设置步长属性。

    ```html
    monthObject.step = number
    ```

**属性值:**它包含一个值，即**号**，该值指定了月份字段的法定月份间隔。它的默认值是 1。

**返回值:**返回一个数值，代表月字段的法定月间隔。

**示例-1:** 本示例说明了如何**返回**属性。

```html
<!DOCTYPE html>
<html>

<body style="text-align:center;">

    <h1 style="color:green;"> 
            GeeksForGeeks 
        </h1>

    <h2>
      DOM InputMonth step Property
  </h2>

    <input type="month" 
           id="month_id" 
           step="3" 
           placeholder="Every 3rd month">
    <br>
    <br>
    <button onclick="myFunction()">
        Click Here!
    </button>

    <p id="gfg"
       style="font-size:23px;
              color:green;">
  </p>

    <script>
        function myFunction() {

            // Accessing input value 
            var x =
                document.getElementById(
                  "month_id").step;
            document.getElementById(
              "gfg").innerHTML = x;
        }
    </script>

</body>

</html>
```

**输出:**(从第 1 个月开始每 3 个月只能选择一次)
**点击按钮前:**
![](img/9ab769f050b795e821e30a29f4007dcb.png)

**点击按钮后:**
![](img/6f9a74cbb742715f5b17cebc2c502ba8.png)

**示例-2 :** 本示例说明如何**设置**属性。

```html
<!DOCTYPE html>
<html>

<body style="text-align:center;">

    <h1 style="color:green;"> 
            GeeksForGeeks 
        </h1>

    <h2>
      DOM Input Month step Property
  </h2>

    <input type="month" 
           id="month_id" 
           step="5" 
           placeholder="multiples of 5">
    <br>
    <br>
    <button onclick="myFunction()">
        Click Here!
    </button>

    <p id="gfg" 
       style="font-size:23px;
              color:green;">
  </p>

    <script>
        function myFunction() {

            // Set step value 
            var x =
                document.getElementById(
                  "month_id").step = "3";

            document.getElementById("gfg").innerHTML =
                "The value of the step attribute "+
              "was changed to " + x;
        }
    </script>

</body>

</html>
```

**输出:**
**点击按钮前:**
![](img/9ab769f050b795e821e30a29f4007dcb.png)

**点击按钮后:**
![](img/2c308cb00d9cf4efce4fcd1acf2fe8f0.png)

**支持的浏览器:**T2 DOM 输入月步属性支持的浏览器如下:

*   谷歌 Chrome
*   Internet Explorer 10.0 +
*   歌剧
*   旅行队