# HTML | DOM WheelEvent deltaMode 属性

> 原文:[https://www . geesforgeks . org/html-DOM-wheel event-delta mode-property/](https://www.geeksforgeeks.org/html-dom-wheelevent-deltamode-property/)

**DOM WheelEvent deltaMode 属性**用于返回一个代表滚动值长度单位的数字，即 **deltaX，deltaY，deltaZ。**只读属性。
它返回三个数值，即:

*   **0:** 代表像素
*   **1:** 代表线路
*   **2:** 代表页数

**语法:**

```html
event.deltaMode 
```

**返回值:**返回一个代表增量值长度单位的数值。

**示例:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>
      DOM WheelEvent deltaMode Property
  </title>
</head>

<body onwheel="Geeks(event)" 
      style="text-align: center; 
             width: 1000px;">

    <h1 style="color: green;"> 
        GeeksforGeeks 
    </h1>

    <h2> 
        DOM WheelEvent deltaMode Property 
    </h2>

    <p>Scroll to see effect:</p>

    <p id="p"></p>

    <script>
        function Geeks(event) {
            var doc = event.deltaMode;
            document.getElementById(
              "p").innerHTML = doc;
        }
    </script>

</body>

</html>
```

**输出:**
**前滚:**
![](img/8c26e4629c1eb9c683328ee9b5097a18.png)

**卷轴后:**
![](img/def48c9ec8f68c0393a363220a14e662.png)

**支持的浏览器:**T2 DOM WheelEvent delta mode 属性支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧