# HTML | DOM 按钮表单方法属性

> 原文:[https://www . geesforgeks . org/html-DOM-button-form method-property/](https://www.geeksforgeeks.org/html-dom-button-formmethod-property/)

**HTML DOM 按钮表单方法属性**用于设置或返回按钮元素的表单方法属性的值。formMethod 属性用于指定在提交表单时用于发送数据的 HTTP 方法。HTTP 方法有两种，GET 和 POST。该属性覆盖了<表单>元素的方法属性。

**语法:**

*   它返回按钮表单方法属性。

    ```html
    ButtonObject.formMethod
    ```

*   它用于设置按钮表单方法属性。

    ```html
    ButtonObject.formMethod = get|post
    ```

**属性值:**

*   **GET:** 在 GET 方法中，表单提交后，表单值会在新浏览器选项卡的地址栏中可见。
*   **POST:** 在 POST 方法中，表单提交后，表单值在新浏览器选项卡的地址栏中将不会像在 GET 方法中一样可见。

**返回值:**返回一个字符串值，代表提交表单时发送数据的 HTTP 方法。

**示例 1:** 本示例说明如何返回 Button formMethod 属性。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML DOM Button formMethod Property
    </title>
</head>

<body style="text-align:center;">
    <h1> 
        GeeksForGeeks 
    </h1>

    <h2> 
        HTML DOM Button formMethod Property 
    </h2>

    <form action="#" method="get" target="_self">
        <button type="submit"
                id="Geeks"
                name="myGeeks"
                value="Submit @ geeksforgeeks"
                formenctype="multipart/form-data"
                formTarget="_blank"
                formMethod="Get"
                Formnovalidate>
            Submit </button>
    </form>

    <p>
        click on below button to return the Property
    </p>

    <button onclick="myGeeks()">
        Click Here!
    </button>

    <p id="GFG" style="font-size:25px;"></p>

    <!-- Script to return formMethod Property -->
    <script>
        function myGeeks() {
            var btn = document.getElementById("Geeks").formMethod;
            document.getElementById("GFG").innerHTML = btn;
        }
    </script>
</body>

</html>
```

**输出:**
**点击按钮前:**
![](img/15c89a2a4cf638af13be345423162e04.png)

**点击按钮后:**
![](img/1d54f1bd86fb05b344dd7ef5c01f956e.png)

**示例 2:** 本示例说明如何返回 Button formMethod 属性。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML DOM Button formMethod Property
    </title>
</head>

<body style="text-align:center;">
    <h1> 
        GeeksForGeeks 
    </h1>

    <h2> 
        HTML DOM Button formMethod Property 
    </h2>

    <form action="#" method="get" target="_self">
        <button type="submit" 
                id="Geeks"
                name="myGeeks"
                value="Submit @ geeksforgeeks"
                formenctype="multipart/form-data"
                formTarget="_blank" 
                formMethod="Get" 
                Formnovalidate>
            Submit </button>
    </form>

    <p>
        click on below button to set the Property
    </p>

    <button onclick="myGeeks()">
        Click Here!
    </button>

    <p id="GFG" style="font-size:25px;"></p>

    <!-- Script to return formMethod Property -->
    <script>
        function myGeeks() {
            var btn = document.getElementById(
              "Geeks").formMethod = "post";

            document.getElementById("GFG").innerHTML =
              "The value of the formmethod attribute" +
              " was changed to " + btn;
        }
    </script>
</body>

</html>
```

**输出:**
**点击按钮前:**
![](img/19c6d74a99caeebb29a71668b8f6b830.png)

**点击按钮后:**
![](img/c7ffd34b921adfde07207d3759b9172f.png)

**支持的浏览器:****HTML DOM 按钮表单方法属性**支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   苹果 Safari
*   歌剧