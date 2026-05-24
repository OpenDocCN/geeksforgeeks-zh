# HTML | DOM 下标对象

> 原文:[https://www.geeksforgeeks.org/html-dom-subscript-object/](https://www.geeksforgeeks.org/html-dom-subscript-object/)

HTML DOM 中的下标对象用来表示 HTML sub 元素。下标元素可以通过使用 getElementById()方法来访问。

**语法:**

```html
document.getElementById("id")
```

其中 id 被分配给<sub>标签。</sub>

**例 1:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
    <head>
        <title>
            HTML DOM subscript Object
        </title>
    </head>

    <body style = "text-align:center">

        <h1 style = "color:green;" >
            GeeksForGeeks
        </h1>

        <h2>DOM subscript Object</h2>

<p>A<sub id = "sub_scr">computer science</sub>
        portal for geeks.</p>

        <button onclick = "Geeks()">
            Click Here
        </button>

        <!-- script to set style to subscript object -->
        <script>
            function Geeks() {
                var txt = document.getElementById("sub_scr");
                txt.style.color = "green";
            }
        </script>
    </body>
</html>                   
```

**输出:**
**之前点击按钮:**

![sub](img/ab9154a222d5b8c2c4fdd0e22be33154.png)

**点击按钮后:**

![sub](img/cecc3fed640c020f7f5f886f9eb88259.png)

**例 2:** 下标对象可以使用 document.createElement 方法创建。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
    <head>
        <title>
            HTML DOM subscript Object
        </title>
    </head>

    <body>
        <center>
        <h1 style = "color:green;" >
            GeeksForGeeks
        </h1>

        <h2>DOM subscript Object</h2>

        <button onclick = "Geeks()">
            Click Here!
        </button>

        <br><br>

        <div>
            A <span id = "p"></span>
            portal for geeks.
        </div>

        <script>
            function Geeks() {
            var txt = document.createElement("SUB");
            var t = document.createTextNode("computer science");
            txt.appendChild(t);
            document.getElementById("p").appendChild(txt);
            }
        </script>
    </body>
</html>                   
```

**输出:**
**之前点击按钮:**

![sub](img/a0ea67ed66817a1387e5049036c49353.png)

**点击按钮后:**

![sub](img/7def9037b623ffad7b03b8e454b77a6f.png)

**支持的浏览器:**

*   歌剧
*   微软公司出品的 web 浏览器
*   谷歌 Chrome
*   火狐浏览器
*   苹果 Safari