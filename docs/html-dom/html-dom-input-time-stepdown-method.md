# HTML | DOM 输入时间步降()方法

> 原文:[https://www . geesforgeks . org/html-DOM-输入-时间-降压-方法/](https://www.geeksforgeeks.org/html-dom-input-time-stepdown-method/)

HTML DOM 中的 **DOM 输入时间步降()方法**用于*将时间字段的值减少给定的数字*。它只会影响分钟数(而不是小时、秒或毫秒)。

**语法:**

```html
timeObject.stepDown(number)
```

**参数:**它接受一个单一且必需的参数:

*   **数字**:指定减少的分钟数。默认情况下，它递减 1。

**返回值:**不返回值。

**示例:**本示例展示了 **stepDown()方法**的工作原理:

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML DOM Input Time stepDown() Method
    </title>
</head>

<body style="text-align:center;">

    <h1>
      GeeksForGeeks
  </h1>

    <h2>
      DOM Input Time stepDown() Method
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
              "time_id").stepDown(3);
        }
    </script>
</body>

</html>
```

**输出:**
**点击按钮前:**
![](img/bbf80cb14c9c0c0983d0228ad4c23815.png)

**点击按钮后:**
![](img/40827b24bccbb43bed72ded15a8e79cc.png)

**支持的浏览器:**T2 DOM 输入时间步降()方法支持的浏览器如下:

*   谷歌 Chrome
*   Internet Explorer 10.0 +
*   歌剧
*   旅行队