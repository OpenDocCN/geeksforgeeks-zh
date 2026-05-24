# HTML | DOM 输入搜索最大长度属性

> 原文:[https://www . geesforgeks . org/html-DOM-input-search-maxlength-property/](https://www.geeksforgeeks.org/html-dom-input-search-maxlength-property/)

HTML DOM 中的 **DOM 输入搜索最大长度属性**用于**设置**或**返回** *搜索输入字段*的最大长度属性值。它指定搜索字段中允许的最大字符数。Input search maxLength 属性的默认值为 **524288** 。

**语法:**

*   它返回输入搜索最大长度属性。

    ```html
    searchObject.maxLength
    ```

*   它用于设置输入搜索最大长度属性。

    ```html
    searchObject.maxLength = number
    ```

**属性值:**它包含单个数值，用于指定搜索最大长度字段中允许的最大字符数。

**返回值:**返回一个数值，代表搜索最大长度字段中允许的最大字符数。

**示例-1:** 本示例说明如何返回 Input 搜索 maxLength 属性。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
      Input Search maxLength Property
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
    <h2>Input Search maxLength Property</h2>
    <form id="myGeeks">
        <input type="Search" 
               id="test" 
               name="myGeeks"
               placeholder="Type to search.." 
               maxlength="45">
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
                "test").maxLength;

            document.getElementById(
                "check").innerHTML = s;
        }
    </script>

</body>

</html>
```

**输出:**
**点击按钮前:**
![](img/c636ec6c5e41daf812a8684a6c4d411d.png)

**点击按钮后:**
![](img/9f9b239232c9df9effb41ee51184f020.png)

**示例-2:** 本示例说明如何**设置**输入搜索最大长度属性。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
      Input Search maxLength Property
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
    <h2>Input Search maxLength Property</h2>
    <form id="myGeeks">
        <input type="Search"
               id="test"
               name="myGeeks"
               placeholder="Type to search.."
               maxlength="45">
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
                "test").maxLength = "60";

            document.getElementById(
                "check").innerHTML = 
       "The value of the maxLength attribute was changed to "
            + s;
        }
    </script>

</body>

</html>
```

**输出:**

**点击按钮前:**
![](img/c636ec6c5e41daf812a8684a6c4d411d.png)

**点击按钮后:**
![](img/10d3bac4b85b2d57e3abf800f2450f05.png)

**支持的浏览器:**T2 DOM 输入搜索 maxLength 属性支持的浏览器如下:

*   谷歌 Chrome
*   Internet Explorer 10.0 +
*   火狐浏览器
*   歌剧
*   旅行队