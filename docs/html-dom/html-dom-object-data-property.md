# HTML | DOM 对象数据属性

> 原文:[https://www . geesforgeks . org/html-DOM-object-data-property/](https://www.geeksforgeeks.org/html-dom-object-data-property/)

**HTML | DOM 对象数据属性**用于**设置**或**返回** *一个<对象>元素*的数据属性值。**数据属性**用于指定对象将要使用的资源的网址。
**语法:**

*   返回数据属性。

```html
objObject.data
```

*   它用于设置数据属性。

```html
objObject.data = URL
```

**属性值:**包含指定资源网址的值，即**网址**。

*   **绝对 URL:** 用于指向另一个网站。
*   **相对网址:**指向网站内的链接。

**返回值:**返回一个代表对象网址的字符串。返回完整的网址，包括协议(如 http://)

**示例:**本示例返回一个数据属性。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body>
    <center>

        <object id="myobject"
                data="HelloGeeks.swf"
                width="400"
                height="100"
                name="myGeeks"
                form="myGeeks"
                data=
"https://media.geeksforgeeks.org/wp-content/uploads/geek-8.png">
      </object>

        <h2>DOM Object data Property</h2>

        <button onclick="Geeks()">
            Click it
        </button>

        <p id="gfg"
           style="color:green;
                  font-size:25px;">
      </p>

    </center>
    <script>
        function Geeks() {

            // Accessing Object element.
            var x =
                document.getElementById(
                    "myobject").data;

            document.getElementById(
                "gfg").innerHTML = x;
        }
    </script>

</body>

</html>
```

**输出:**
**点击按钮前:**

![](img/bcae1677951e0948bb78217e3fad7471.png)

**点击按钮后:**

![](img/b26b202abb66a5342befb89bc3d370cb.png)

**支持的浏览器:**

*   谷歌 Chrome
*   Mozilla Firefox
*   边缘
*   旅行队
*   歌剧