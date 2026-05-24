# HTML | DOM 输入 URL 所需属性

> 原文:[https://www . geesforgeks . org/html-DOM-input-URL-required-property/](https://www.geeksforgeeks.org/html-dom-input-url-required-property/)

HTML DOM 中的 **DOM 输入 URL 必填属性**用于**设置**或**返回**提交表单时是否应填写输入 **url** 字段。此属性用于反映 HTML 必需的属性。
**语法:**

*   它返回需要输入网址的属性。

```html
urlObject.required
```

*   它用于设置需要输入网址的属性。

```html
urlObject.required = true|false
```

**属性值:**

*   **true:** 指定提交表单前必须填写 url 字段。
*   **false:** 为默认值。它指定在提交表单之前不得填写 url 字段。

**返回值:**返回一个布尔值，表示提交表单前是否必须填写网址字段。
**示例-1:** 此示例说明如何返回 Input url 必需属性。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        DOM Input URL required Property
    </title>
</head>

<body>
    <center>
        <h1 style="color:green;">
                GeeksForGeeks
            </h1>

        <h2>
          DOM Input URL required Property
      </h2>

        <label for="uname"
               style="color:green">
            <b>Enter URL</b>
        </label>

        <input type="url"
               id="gfg"
               placeholder="Enter URL"
               size="20"
               required>

        <br>
        <br>

        <button type="button"
                onclick="geeks()">
            Click
        </button>

        <p id="GFG"
           style="color:green;
                  font-size:25px;">
      </p>

        <script>
            function geeks() {

                var link =
                    document.getElementById(
                  "gfg").required;

                document.getElementById(
                  "GFG").innerHTML =
                  link;
            }
        </script>
    </center>
</body>

</html>
```

**输出:**
**点击按钮前:**

![](img/9c4139a32c31e5e4c4045d0a34692283.png)

**点击按钮后:**

![](img/448347f20633653b4a1b5446a8f42ca3.png)

**示例-2:** 本示例说明如何**设置**输入网址所需的属性。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        DOM Input URL required Property
    </title>
</head>

<body>
    <center>
        <h1 style="color:green;">
                GeeksForGeeks
            </h1>

        <h2>
          DOM Input URL required Property
      </h2>

        <label for="uname" style="color:green">
            <b>Enter URL</b>
        </label>

        <input type="url"
               id="gfg"
               placeholder="Enter URL"
               size="20"
               required>

        <br>
        <br>

        <button type="button"
                onclick="geeks()">
            Click
        </button>

        <p id="GFG"
           style="color:green;
                  font-size:25px;">
      </p>

        <script>
            function geeks() {

                // Set URL required property.
                var link =
                    document.getElementById(
                      "gfg").required = "false";

                document.getElementById(
                  "GFG").innerHTML = link;
            }
        </script>
    </center>
</body>

</html>
```

**输出:**
**点击按钮前:**

![](img/9c4139a32c31e5e4c4045d0a34692283.png)

**点击按钮后:**

![](img/9e309452632d3233644c7d32870749c6.png)

**支持的浏览器:****DOM 输入 URL 所需属性**支持的浏览器如下:

*   谷歌 Chrome
*   Internet Explorer 10.0 +
*   火狐浏览器
*   歌剧
*   旅行队