# HTML | DOM 输入按钮值属性

> 原文:[https://www . geesforgeks . org/html-DOM-input-button-value-property/](https://www.geeksforgeeks.org/html-dom-input-button-value-property/)

HTML DOM 中的 **DOM 输入按钮值属性**用于**设置**或**返回** *按钮字段*的值属性的值。值属性指定按钮上显示的文本。

**语法:**

*   它返回 value 属性。

    ```html
    buttonObject.value
    ```

*   它用于设置 value 属性。

    ```html
    buttonObject.value = text
    ```

**属性值:**包含定义输入按钮字段值的单值文本。

**返回值:**返回代表按钮字段值的字符串值。

**示例-1:** 这个示例说明了如何返回属性。

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        h1 {
            color: green;
        }
    </style>
</head>

<body style="text-align:center;">
    <h1>
      GeeksForGeeks
  </h1>
    <h2> 
      DOM Input Button value Property 
  </h2>

    <!-- Assigning button id -->
    <input type="button"
           id="GFG"
           onclick="myGeeks()"
           value="Submit">

    <p id="sudo" 
       style="color:green;
              font-size:25px;">
  </p>

    <script>
        function myGeeks() {

            // accessing 'button' id. 
            var g = 
                document.getElementById(
                  "GFG").value;

            document.getElementById(
              "sudo").innerHTML = g;
        }
    </script>

</body>

</html>
```

**输出:**
**点击按钮前:**
![](img/c0ec44004d5836f19272dfa62303f0e7.png)

**点击按钮后:**
![](img/b0105ed62e449d97ccb4566c39b38c7d.png)

**示例-2:** 本示例说明如何**设置**属性。

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        h1 {
            color: green;
        }
    </style>
</head>

<body style="text-align:center;">
    <h1>GeeksForGeeks</h1>
    <h2> 
      DOM Input Button value Property 
  </h2>

    <!-- Assigning button id -->
    <input type="button"
           id="GFG" 
           onclick="myGeeks()"
           value="Submit">

    <p id="sudo"
       style="color:green;
              font-size:25px;">
  </p>

    <script>
        function myGeeks() {

            // accessing 'button' id. 
            var g = 
                document.getElementById(
                  "GFG").value = "click here";

            document.getElementById(
              "sudo").innerHTML = 
              "The value was changed to " + g;
        }
    </script>

</body>

</html>
```

**输出:**
**点击按钮前:**
![](img/c0ec44004d5836f19272dfa62303f0e7.png)

**点击按钮后:**
![](img/d89135106a9e8f0700f1f49e7f331ece.png)

**支持的浏览器:****DOM 输入按钮值属性**支持的浏览器如下:

*   谷歌 Chrome
*   Internet Explorer 10.0 +
*   火狐浏览器
*   歌剧
*   旅行队