# HTML | DOM 输入时间步长()方法

> 原文:[https://www . geesforgeks . org/html-DOM-input-time-step-method/](https://www.geeksforgeeks.org/html-dom-input-time-stepup-method/)

HTML DOM 中的 **DOM 输入时间步长()方法**用于*将时间字段的值增加给定的数字*。它只会影响分钟数(而不是小时、秒或毫秒)。

**语法:**

```html
timeObject.stepUp(number)
```

**参数:**它接受一个单一且必需的参数:

*   **数字**:指定需要增加的分钟数。默认情况下，它会增加 1。

**返回值:**不返回值。

**例:**本例展示了 **stepUp()方法**的工作原理:

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML DOM Input Time stepUp() Method
    </title>
</head>

<body style="text-align:center;">

    <h1>
      GeeksForGeeks
  </h1>

    <h2>
      DOM Input Time stepUp() Method
  </h2>
    <form id="myGeeks">
        <input type="time" 
               id="time_id" 
               name="geeks" 
               value="09:25:37">
    </form>
    <br>
    <button onclick="myGeeks()">
      Click Here!
  </button>

    <!-- Script to increment the minutes -->
    <script>
        function myGeeks() {
            document.getElementById(
              "time_id").stepUp(3);
        }
    </script>
</body>

</html>
```

**输出:**
**点击按钮前:**
![](img/51c730dcbb58e56759ab7266c66a3c94.png)

**点击按钮后:**
![](img/36c38cb6c3b36bdedc0aa0c28ffa9599.png)

**支持的浏览器:**T2 DOM 输入时间步长()方法支持的浏览器如下:

*   谷歌 Chrome
*   Internet Explorer 10.0 +
*   歌剧
*   旅行队