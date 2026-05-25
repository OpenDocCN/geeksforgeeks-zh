# HTML DOM touch event targetTouches 属性

> 原文：[https://www.geeksforgeeks.org/html-dom-touchevent-targettouches-property/](https://www.geeksforgeeks.org/html-dom-touchevent-targettouches-property/)

`targetTouches` 属性是只读属性，用于返回触摸对象的数组。它为接触当前目标元素的每个手指返回一个对象。

**语法：**

```html
event.targetTouches
```

下面的程序说明了 `targetTouches` 属性：

**示例：** 找出触摸一个元素的手指数量。

```html
<!DOCTYPE html>
<html>
<meta name="viewport" content="width=device-width, initial-scale=1">

<head>
    <title> TouchEvent targetTouches property in HTML
  </title>

<style>
        #samplediv {
            border: 1px solid green;
        }

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

<body ontouchstart="countTouches(event)" ontouchend="countTouches(event)">

<h1>GeeksforGeeks</h1>
    <h2> TouchEvent targetTouches property </h2>
    <br>

<p>The current element is touched by <span id="touch">0</span> fingers.</p>

<script>
        function countTouches(event) {
            //  Returning touched target.
            var t = event.targetTouches.length;
            document.getElementById("touch").innerHTML = t;
        }
    </script>

</body>

</html>
```

**输出：**

**触摸屏幕后：**
![](img/03fb6cad6e2e4000ace92f56a43a490f.png)

**触摸屏幕后：**
![](img/45c1d016137b01eee0b4dead3db13f91.png)

**支持的浏览器：**

*   Opera
*   Microsoft Edge
*   Google Chrome
*   Firefox
*   Safari