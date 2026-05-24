# HTML | DOM onmousedown 事件

> 原文:[https://www.geeksforgeeks.org/html-dom-onmousedown-event/](https://www.geeksforgeeks.org/html-dom-onmousedown-event/)

**HTML DOM onmousedown 事件**发生在按下元素上的鼠标按钮时。
**相关事件为左键:**

*   onmousedown
*   是 mouseup
*   onclick

**相关事件为右键:**

*   onmousedown
*   是 mouseup
*   oncontextmenu

**支持的标签:支持所有 HTML 元素，除了:**

*   **T2>基地**
*   **<【bdo】>**
*   **<【br】>**
*   **<头像>**
*   **< html >**
*   **< iframe >**
*   **< 当 >**
*   **<停止>**
*   **<剧本>**
*   **<风格>**
*   **<称号>**

**语法:**

*   **在 HTML 中:**

```html
<element onmousedown="myScript">
```

*   **在 JavaScript 中:**

```html
object.onmousedown = function(){myScript};
```

*   **在 JavaScript 中，使用 addEventListener()方法:**

```html
object.addEventListener("mousedown", myScript);
```

**示例:**使用 addEventListener()方法

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
      HTML DOM onmousedown Event
  </title>
</head>

<body>
    <center>
        <h1 style="color:green">
          GeeksforGeeks
      </h1>
        <h2 id="try">
          HTML DOM onmousedown Event
      </h2>

        <script>
            document.getElementById(
              "try").addEventListener(
              "mousedown", btnpressed);

            function btnpressed() {
                document.getElementById(
                  "try").innerHTML =
                  "button pressed.";
            }
        </script>
    </center>
</body>

</html>
```

**输出:**

![](img/3a999a29ab49da20d603835e2cd96bc8.png)

**支持的浏览器:****HTML DOM on mousedown Event**支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   苹果 Safari
*   歌剧