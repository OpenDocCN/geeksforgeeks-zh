# HTML | DOM 输入范围 stepUp()方法

> 原文:[https://www . geesforgeks . org/html-DOM-input-range-step-method/](https://www.geeksforgeeks.org/html-dom-input-range-stepup-method/)

HTML DOM 中的 **DOM 输入范围步进()方法**用于*将滑块控件的值增加给定的数字*。

**语法:**

```html
rangeObject.stepUp(number)
```

**参数:**它接受一个单一且必需的参数:

*   **号**:指定需要增加的滑块控件的数量。默认情况下，它会增加 1。

**返回值:**不返回值。

**例:**本例展示了 **stepUp()方法**的工作原理:

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML DOM Input Range stepUp() Method
    </title>
</head>

<body style="text-align:center;">

    <h1>
      GeeksForGeeks
  </h1>

    <h2>
      DOM Input Range stepUp() Method
  </h2>
    <form id="myGeeks">
        <input type="range" 
               id="range_id"
               name="geeks" 
               value="70">
    </form>
    <br>
    <button onclick="myGeeks()">
      Click Here!
  </button>

    <!-- Script to increment the range -->
    <script>
        function myGeeks() {
            document.getElementById(
              "range_id").stepUp(3);
        }
    </script>
</body>

</html>
```

**输出:**
**点击按钮前:**
![](img/cfc6fa49ea976ea6e01191fe62aabfa0.png)

**点击按钮后(10 次):**
![](img/be3432eba78fad0bdfe3442b1c7cdc45.png)

**支持的浏览器:**T2 DOM 输入范围 stepUp()方法支持的浏览器如下:

*   谷歌 Chrome
*   Mozilla Firexox
*   Internet Explorer 10.0 +
*   歌剧
*   旅行队