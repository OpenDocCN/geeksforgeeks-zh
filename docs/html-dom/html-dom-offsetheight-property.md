# HTML | DOM offset 权限属性

> 原文:[https://www . geesforgeks . org/html-DOM-offsetheight-property/](https://www.geeksforgeeks.org/html-dom-offsetheight-property/)

**DOM offset thight 属性**用于以整数形式返回元素的布局高度。它以像素为单位。它包括高度、边框、填充和水平滚动条，但不包括边距。如果元素被隐藏，那么它返回 0。

**语法:**

```html
element.offsetHeight 
```

**返回值:**以整数形式返回元素的布局高度。

**例 1:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        DOM Style offsetHeight Property
    </title>

    <style>
        #GFG {
            height: 150px;
            width: 300px;
            padding: 10px;
            margin: 15px;
            background-color: green;
        }
    </style>
</head>

<body>
    <h2>DOM offsetHeight Property</h2>

    <div id="GFG">
        <b>Information about this div:</b>

        <p id="sudo"></p>

    </div>

    <button type="button" onclick="Geeks()">
        Submit
    </button>

    <script>
        function Geeks() {

            var element = document.getElementById("GFG");

            var txt = "Height including padding and border: "
                + element.offsetHeight + "px";

            document.getElementById("sudo").innerHTML = txt;
        }
    </script>
</body>

</html>
```

**输出:**

*   **点击按钮前:**

![](img/6334980708376dd776fdb7d43706ce56.png)

*   **点击按钮后:**

![](img/b8e90448032314e37796fd98739a3ccc.png)

**示例-2:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        DOM Style offsetHeight Property
    </title>

    <style>
        #GFG {
            height: 150px;
            width: 300px;
            padding: 10px;
            margin: 15px;
            background-color: green;
        }
    </style>
</head>

<body>
    <h2>DOM offsetHeight Property</h2>

    <div id="GFG">
        <b>Information about this div:</b>
        <br>

        <p id="sudo"></p>

    </div>

    <button type="button" onclick="Geeks()">
        Submit
    </button>

    <script>
        function Geeks() {
            var element = document.getElementById("GFG");
            var txt = "";
            txt += "Height with padding: "
                + element.clientHeight + "px<br>";

            txt += "Height with padding and border: "
                + element.offsetHeight + "px";

            document.getElementById("sudo").innerHTML = txt;
        }
    </script>
</body>

</html>
```

**输出:**

*   **点击按钮前:**

![](img/89cf4e27ca31ed5dd59c23a861deff1e.png)

*   **点击按钮后:**

![](img/5da1b263dac73682dc27c367502cf01c.png)

**支持的浏览器:**T2 DOM offset 权限属性支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队