# HTML | DOM 输入单选名称属性

> 原文:[https://www . geesforgeks . org/html-DOM-input-radio-name-property/](https://www.geeksforgeeks.org/html-dom-input-radio-name-property/)

HTML DOM 中的 **DOM 输入单选按钮名称属性**用于**设置**或**返回** *单选按钮*的名称属性值。每个输入字段都需要名称属性。如果没有在输入字段中指定 name 属性，则根本不会发送该字段的数据。

**语法:**

*   它返回输入无线电名称属性。

    ```html
    radioObject.name
    ```

*   它用于设置输入无线电名称属性。

    ```html
    radioObject.name = name
    ```

**属性值:**它包含一个定义单选按钮名称的值名。

**返回值:**返回代表单选按钮名称的字符串值。

**示例-1:** 本示例说明如何**返回**输入电台名称属性。

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        body {
            text-align: center;
        }

        h1 {
            color: green;
        }
    </style>
</head>

<body>
    <h1>
      GeeksforGeeks
  </h1>

    <h2>
      HTML DOM Input Radio name Property
  </h2> 
  Radio Button:
    <input type="radio" 
           checked=true 
           id="radioID"
           value="Geeks_radio" 
           name="Geek_radio">
    <br>
    <br>
    <button onclick="GFG()">
        Click!
    </button>
    <p id="GFG"
       style="font-size:25px;
              color:green;">
  </p>
    <script>
        function GFG() {

            // Accessing input element 
            // type="radio" 
            var x =
                document.getElementById(
                  "radioID").name;

            document.getElementById(
              "GFG").innerHTML = x;
        }
    </script>

</body>

</html>
```

**输出:**
**点击按钮前:**
![](img/becd3f115d71842482e353bf9512dc32.png)

**点击按钮后:**
![](img/2666db1428d234fe9061af8b4fafd406.png)

**示例-2:** 本示例说明如何**设置**属性。

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        body {
            text-align: center;
        }

        h1 {
            color: green;
        }
    </style>
</head>

<body>
    <h1>
      GeeksforGeeks
  </h1>

    <h2>
      HTML DOM Input Radio name Property
  </h2> 
  Radio Button:
    <input type="radio"
           checked=true 
           id="radioID"
           value="Geeks_radio"
           name="Geek_radio">
    <br>
    <br>
    <button onclick="GFG()">
        Click!
    </button>
    <p id="GFG"
       style="font-size:25px;
              color:green;">
  </p>
    <script>
        function GFG() {

            // Accessing input element 
            // type="radio" 
            var x =
                document.getElementById(
                  "radioID").name = "myGeeks";

            document.getElementById(
              "GFG").innerHTML = 
              "The value of the name attribute"+
              " was changed to " + x;
        }
    </script>

</body>

</html>
```

**输出:**

**点击按钮前:**
![](img/becd3f115d71842482e353bf9512dc32.png)

**点击按钮后:**
![](img/8eaacf373187fcdf485aa2decfe9d5c2.png)

**支持的浏览器:**T2 DOM 输入电台名称属性支持的浏览器如下:

*   谷歌 Chrome
*   Internet Explorer 10.0 +
*   火狐浏览器
*   歌剧
*   旅行队