# HTML | DOM 样式边框颜色属性

> 原文:[https://www . geeksforgeeks . org/html-DOM-style-borderrightcolor-property/](https://www.geeksforgeeks.org/html-dom-style-borderrightcolor-property/)

borderRightColor 属性允许我们设置/获取元素右边框的颜色。
**语法:**

*   它用于返回 borderRightColor 属性。

```html
object.style.borderRightColor
```

*   它用于返回 borderRightColor 属性。

```html
object.style.borderRightColor = "color|transparent|initial|inherit"
```

**返回值:**borderRightColor 属性返回元素右边框的颜色。
**房产价值:**

*   **颜色:**指定对应元素的右边框颜色。黑色是默认颜色。
    *   **语法:**

```html
borderRightColor = "red"
```

*   **示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        #GFG_Div {
            width: 200px;
            margin-left: 210px;
            border: thick solid green;
        }
    </style>
</head>

<body align="center">

<p> Click to change the right border color of element.</p>

    <button type="button" onclick="myGeeks()">
        Click to change
    </button>
    <br>
    <br>
    <div id="GFG_Div">GeeksforGeeks</div>
    <script>
        function myGeeks() {
            document.getElementById("GFG_Div")
                .style.borderRightColor = "red";
        }
    </script>

</body>

</html>
```

*   **输出:**
    *   点击按钮
        前

![](img/40189f13815b9f8c482e06c3ce1902cb.png)

*   点击按钮后

![](img/e521da0e8caba9a58211c102c37c10f2.png)

*   **语法:**

```html
borderRightColor = "yellow"
```

*   **示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        #GFG_Div {
            width: 200px;
            margin-left: 210px;
            border: thick solid green;
        }
    </style>
</head>

<body align="center">

<p> Click to change the right border color of element.</p>

    <button type="button" onclick="myGeeks()">
        Click to change
    </button>
    <br>
    <br>
    <div id="GFG_Div">GeeksforGeeks</div>
    <script>
        function myGeeks() {
            document.getElementById("GFG_Div")
                .style.borderRightColor = "yellow";
        }
    </script>

</body>

</html>
```

*   **输出:**
    *   点击按钮前

![](img/40189f13815b9f8c482e06c3ce1902cb.png)

*   点击按钮后

![](img/94eb59118f94a35bbac2af88065522dc.png)

*   **透明:**将对应元素的右边框颜色设置为透明。
    *   **语法:**

```html
borderRightColor = "transparent"
```

*   **示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        #GFG_Div {
            width: 200px;
            margin-left: 210px;
            border: thick solid green;
        }
    </style>
</head>

<body align="center">

<p> Click to change the right border color of element.</p>

    <button type="button" onclick="myGeeks()">
        Click to change
    </button>
    <br>
    <br>
    <div id="GFG_Div">GeeksforGeeks</div>
    <script>
        function myGeeks() {
            document.getElementById("GFG_Div")
                .style.borderRightColor = "transparent";
        }
    </script>

</body>

</html>
```

*   **输出:**
    *   点击按钮前

![](img/40189f13815b9f8c482e06c3ce1902cb.png)

*   点击按钮后

![](img/fdf2d665f0b54a7957c7446f783b3212.png)

*   **初始值:**当没有为此字段指定值时，从元素的父元素继承。如果没有父元素意味着这个元素是根元素，那么它采用初始值(或缺省值)。
*   **inherit:** 此关键字将属性的初始值(或默认值)应用于元素。初始值不应与浏览器样式表指定的值混淆。当边框颜色设置为初始时，它显示为黑色(默认)。

**浏览器支持:**DOM Style borderRightColor 属性支持的浏览器如下:

*   谷歌浏览器:支持
*   互联网浏览器:支持
*   Mozilla 火狐:支持
*   Safari:支持
*   歌剧:支持