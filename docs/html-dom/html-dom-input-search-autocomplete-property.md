# HTML | DOM 输入搜索自动完成属性

> 原文:[https://www . geesforgeks . org/html-DOM-input-search-autocomplete-property/](https://www.geeksforgeeks.org/html-dom-input-search-autocomplete-property/)

HTML DOM 中的 **DOM 输入搜索自动完成属性**用于**设置**或**返回** *输入搜索字段*的自动完成属性值。自动完成属性用于指定自动完成属性是**“开”**还是**“关”**值。当“自动完成”属性设置为“开”时，浏览器将根据用户之前输入的值自动完成。

**语法:**

*   它返回输入搜索自动完成属性。

    ```html
    searchObject.autocomplete
    ```

*   它用于设置输入搜索自动完成属性。

    ```html
    searchObject.autocomplete = "on|off"
    ```

**属性值:**

*   **开:**为默认值。它会自动完成这些值。
*   **off:** 定义用户应填写搜索输入字段的值。它不会自动完成这些值。

**返回值:**返回一个代表自动完成状态的字符串值

**示例:**本示例说明如何返回属性。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
      Input Search autocomplete Property
  </title>
    <style>
        h1 {
            color: green;
        }

        h2 {
            font-family: Impact;
        }

        body {
            text-align: center;
        }
    </style>
</head>

<body>

    <h1>GeeksforGeeks</h1>
    <h2>Input Search autocomplete Property</h2>
    <form id="myGeeks">
        <input type="Search"
               id="test"
               name="myGeeks" 
               placeholder="Type to search.." 
               value="GeeksForGeeks" 
               autocomplete="on">
    </form>
    <br>
    <br>
    <button ondblclick="Access()">click here
    </button>

    <p id="check" 
       style="font-size:24px;
              color:green;">
  </p>

    <script>
        function Access() {

            // type="search" 
            var s = document.getElementById(
                "test").autocomplete;

            document.getElementById(
                "check").innerHTML = s;
        }
    </script>

</body>

</html>
```

**输出:**
**点击按钮前:**
![](img/4e7448abf04b1ddc612b56269cc96f59.png)

**点击按钮后:**
![](img/8fe97f0b940b23ffbfbc488a2304a139.png)

**示例-2:** 本示例说明如何**设置**自动完成属性。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
      Input Search autocomplete Property
  </title>
    <style>
        h1 {
            color: green;
        }

        h2 {
            font-family: Impact;
        }

        body {
            text-align: center;
        }
    </style>
</head>

<body>

    <h1>GeeksforGeeks</h1>
    <h2>Input Search autocomplete Property</h2>
    <form id="myGeeks">
        <input type="Search"
               id="test"
               name="myGeeks"
               placeholder="Type to search.." 
               value="GeeksForGeeks"
               autocomplete="on">
    </form>
    <br>
    <br>
    <button ondblclick="Access()">
      click here
    </button>

    <p id="check" 
       style="font-size:24px;
              color:green;">
  </p>

    <script>
        function Access() {

            // type="search" 
            var s = document.getElementById(
                "test").autocomplete = "off";

            document.getElementById(
                "check").innerHTML = 
         "The value of the autocompletee"
            +" attribute was changed to "
            + s;
        }
    </script>

</body>

</html>
```

**输出:**
**点击按钮前:**
![](img/4e7448abf04b1ddc612b56269cc96f59.png)

**点击按钮后:**
![](img/83c9a8a6a49c3f015c49a40ec9b9e1b9.png)

**支持的浏览器:**T2 DOM 输入搜索自动完成属性支持的浏览器如下:

*   谷歌 Chrome
*   Internet Explorer 10.0 +
*   火狐浏览器
*   歌剧
*   旅行队