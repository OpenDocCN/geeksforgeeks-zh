# HTML | DOM 样式边框颜色属性

> 原文:[https://www . geesforgeks . org/html-DOM-style-bordertopcolor-property/](https://www.geeksforgeeks.org/html-dom-style-bordertopcolor-property/)

borderTopColor 属性允许我们设置/获取元素上边框的颜色。
**语法:**

*   它返回 borderTopColor 属性。

```html
object.style.borderTopColor
```

*   它用于设置 borderTopColor 属性。

```html
object.style.borderTopColor = "color|transparent|initial|
inherit"
```

**返回值:**borderTopColor 属性返回元素上边框的颜色。
**房产价值:**

*   **颜色:**指定对应元素的上边框颜色。黑色是默认颜色。
    *   **语法:**

```html
borderTopColor = "red"
```

*   **示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML | DOM Style borderTopColor Property
    </title>
    <style>
        #GFG_Div {
            width: 200px;
            margin-left: 210px;
            border: thick solid green;
        }
    </style>
</head>

<body align="center">

<p>
     Click to change the right border
     color of element.
    </p>

    <button type="button" onclick="myGeeks()">
     Click to change
    </button>
    <br>
    <br>
    <div id="GFG_Div">GeeksforGeeks</div>
    <script>
        function myGeeks() {
            document.getElementById("GFG_Div")
                .style.borderTopColor = "red";
        }
    </script>

</body>

</html>
```

*   **输出:**
    *   点击按钮前

![](img/fe2005d02105af87cfbcc772482a5d84.png)

*   点击按钮后

![](img/92b6e77ae91f104d65b5fdf838e9d5e9.png)

*   **语法:**

```html
borderTopColor = "yellow"
```

*   **示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML | DOM Style borderTopColor Property
    </title>
    <style>
        #GFG_Div {
            width: 200px;
            margin-left: 210px;
            border: thick solid green;
        }
    </style>
</head>

<body align="center">

<p>
     Click to change the top border
     color of element.
    </p>

    <button type="button" onclick="myGeeks()">
     Click to change
    </button>
    <br>
    <br>
    <div id="GFG_Div">GeeksforGeeks</div>
    <script>
        function myGeeks() {
            document.getElementById("GFG_Div")
                .style.borderTopColor = "yellow";
        }
    </script>

</body>

</html>
```

*   **输出:**
    *   点击按钮前

![](img/fe2005d02105af87cfbcc772482a5d84.png)

*   点击按钮后

![](img/9cccda6ec1448ed201e4fc775a096c51.png)

*   **透明:**将对应元素的上边框颜色设置为透明。
    *   **语法:**

```html
borderTopColor = "transparent"
```

*   **示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML | DOM Style borderTopColor Property
    </title>
    <style>
        #GFG_Div {
            width: 200px;
            margin-left: 210px;
            border: thick solid green;
        }
    </style>
</head>

<body align="center">

<p>
      Click to change the right border
      color of element.</p>

    <button type="button" onclick="myGeeks()">
      Click to change
    </button>
    <br>
    <br>
    <div id="GFG_Div">GeeksforGeeks</div>
    <script>
        function myGeeks() {
            document.getElementById("GFG_Div")
                .style.borderTopColor = "transparent";
        }
    </script>

</body>

</html>
```

*   **输出:**
    *   点击按钮前

![](img/fe2005d02105af87cfbcc772482a5d84.png)

*   点击按钮后

![](img/d6f314e2f0f465a0cb2baea554b259b5.png)

*   **初始值:**当没有为此字段指定值时，从元素的父元素继承。如果没有父元素意味着这个元素是根元素，那么它采用初始值(或缺省值)。
*   **inherit:** 此关键字将属性的初始值(或默认值)应用于元素。初始值不应与浏览器样式表指定的值混淆。当边框颜色设置为初始时，它显示为黑色(默认)。

**浏览器支持:**T2 DOM Style borderTopColor 属性支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   Mozilla firefox
*   歌剧
*   旅行队