# HTML | DOM 参数对象

> 原文:[https://www.geeksforgeeks.org/html-dom-parameter-object/](https://www.geeksforgeeks.org/html-dom-parameter-object/)

HTML DOM 中的**映射对象**属性用于创建和访问对象中的 [<参数>](https://www.geeksforgeeks.org/html-param-tag/) 元素。嵌入元素的插件的参数是通过使用元素来实现的。
**语法:**

*   它用于访问<param>元素。

```html
var x = document.getElementById("myParam");
```

*   用于创建<param>元素。

```html
var x = document.createElement("PARAM");
```

**房产价值:**

*   [**名称:**](https://www.geeksforgeeks.org/html-dom-parameter-name-property/) 用于设置或返回参数的名称属性的值。
*   [**值:**](https://www.geeksforgeeks.org/html-dom-parameter-value-property/?ref=rp) 用于设置或返回参数的值属性的值。

**示例-1:** 访问参数元素的名称值。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
    <title>
        HTML DOM Parameter Object Property
    </title>
<body>
    <h4>Click the button</h4>
    <button onclick="GFG()">Click Here!<br>
    </button>

<p></p>

        <object data="sample.mp4">
            <param id="myParam" name="Autoplay" value="true">
        </object>
    <p id="Geeks"></p>

    <script>
        function GFG() {
                   var x = document.getElementById("myParam").name;
           document.getElementById("Geeks").innerHTML = x;
        }
    </script>
</body>
</html>
```

**输出:**

*   **之前点击按钮**
*   **点击按钮后**

**示例-2:** 使用**文档创建参数元素。。** 

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
    <title>
        HTML DOM Menu Object Property
    </title>
<body>
    <h4>Click the button</h4>
    <button onclick="GFG()">Click Here!<br>
    </button>

<p></p>

    <script>
        function GFG() {
            var x = document.createElement("OBJECT");
            x.setAttribute("data", "sample.mp4");
            x.setAttribute("id", "myObject");
            document.body.appendChild(x);

            var y = document.createElement("PARAM");
            y.setAttribute("name", "autoplay");
            y.setAttribute("value", "true");
            document.getElementById("myObject").appendChild(y);   
        }
    </script>
</body>
</html>
```

**输出:**

*   **之前点击按钮**
*   **点击按钮后**

**执行上述代码的步骤:**

*   添加媒体文件。
*   将文件保存在本地。
*   在标准浏览器上运行。

**支持的浏览器:****DOM 参数对象属性**支持的浏览器如下:

*   谷歌 Chrome 5.0
*   Internet Explorer 8.0
*   Firefox 3.6
*   Safari 5.0
*   歌剧 10.6