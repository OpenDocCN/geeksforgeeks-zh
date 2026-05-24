# HTML | DOM 输入搜索名称属性

> 原文:[https://www . geesforgeks . org/html-DOM-input-search-name-property/](https://www.geeksforgeeks.org/html-dom-input-search-name-property/)

HTML DOM 中的 **DOM 输入搜索名称属性**用于**设置**或**返回** *搜索字段*的名称属性值。每个输入字段都需要名称属性。如果没有在输入字段中指定 name 属性，则根本不会发送该字段的数据。

**语法:**

*   它返回输入搜索名称属性。

    ```html
    searchObject.name
    ```

*   它用于设置输入搜索名称属性。

    ```html
    searchObject.name = name
    ```

**属性值:**它包含定义搜索字段名称的单个值名称。

**返回值:**返回一个代表搜索字段名称的字符串值。

**示例-1:** 本示例说明如何返回 Input 搜索名称属性。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
      Input Search name Property
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
    <h2>Input Search name Property</h2>
    <form id="myGeeks">
        <input type="Search"
               id="test"
               name="myGeeks"
               placeholder="Type to search..">
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
                "test").name;

            document.getElementById(
                "check").innerHTML = s;
        }
    </script>

</body>

</html>
```

**输出:**
**点击按钮前:**
![](img/d93d5238972114d79c9e68936ea9918c.png)

**点击按钮后:**
![](img/eb174604893c6f19fc6016efe22510da.png)

**示例-2:** 本示例说明如何**设置**属性。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
      Input Search name Property
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
    <h2>Input Search name Property</h2>
    <form id="myGeeks">
        <input type="Search"
               id="test"
               name="myGeeks" 
               placeholder="Type to search..">
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
                "test").name = "HelloGeeks";

            document.getElementById(
                "check").innerHTML = 
              "The value of the name attribute was changed to "
            + s;
        }
    </script>

</body>

</html>
```

**输出:**
**点击按钮前:**
![](img/f25ef8708eb0049d89e1815546892403.png)

**点击按钮后:**
![](img/ca029380d3a064f309fd6e358593fd80.png)

**支持的浏览器:**T2 DOM 输入搜索名称属性支持的浏览器如下:

*   谷歌 Chrome
*   Internet Explorer 10.0 +
*   火狐浏览器
*   歌剧
*   旅行队