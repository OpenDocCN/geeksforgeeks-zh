# HTML | DOM 输入数字步降()方法

> 原文:[https://www . geesforgeks . org/html-DOM-input-number-step down-method/](https://www.geeksforgeeks.org/html-dom-input-number-stepdown-method/)

HTML DOM 中的 **DOM 输入数字步降()方法**用于*将数字字段的值减少给定值*。

**语法:**

```html
numberObject.stepDown(number)
```

**参数:**它接受一个单一且必需的参数:

*   **数字**:指定数字字段要减少的数字。默认情况下，它递减 1。

**返回值:**不返回值。

**示例:**本示例展示了 **stepDown()方法**的工作原理:

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML DOM Input Number stepDown() Method
    </title>
</head>

<body style="text-align:center;">

    <h1>GeeksForGeeks</h1>

    <h2>
      DOM Input Number stepDown() Method
  </h2>
    <form id="myGeeks">
        <input type="number" 
               id="number_id" 
               name="geeks" 
               value="11">
    </form>
    <br>
    <button onclick="myGeeks()">
      Click Here!
  </button>

    <!-- Script to decrement the number -->
    <script>
        function myGeeks() {
            document.getElementById(
              "number_id").stepDown(3);
        }
    </script>
</body>

</html>
```

**输出:**
**点击按钮前:**
![](img/7b5b5463d815d6410708c7ae13ee172b.png)

**点击按钮后:**
![](img/093e365837e029759bffacf44a68c9c9.png)

**支持的浏览器:**T2 DOM 输入 Number stepDown()方法支持的浏览器如下:

*   谷歌 Chrome
*   Internet Explorer 10.0 +
*   歌剧
*   旅行队