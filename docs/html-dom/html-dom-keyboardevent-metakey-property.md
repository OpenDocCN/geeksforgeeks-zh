# HTML | DOM KeyboardEvent 元键属性

> 原文:[https://www . geesforgeks . org/html-DOM-keyboardevent-meta key-property/](https://www.geeksforgeeks.org/html-dom-keyboardevent-metakey-property/)

HTML DOM 中的 **KeyboardEvent metaKey** 属性是一个只读属性，用于返回一个布尔值，该值用于检查 META 键是否被按下。如果按下了元键，KeyboardEvent 元键属性返回 true，否则返回 false。

**语法:**

```html
event.metaKey
```

下面的程序说明了超文本标记语言文档中的键盘事件元键属性:

**示例:**本示例检查是否按下了 META 键。

```html
<!DOCTYPE html>
<html>

<head> 
    <title>
        HTML DOM KeyboardEvent metaKey Property
    </title> 
</head>

<body>

    <h1>GeeksforGeeks</h1> 

    <h2>KeyboardEvent metaKey Property</h2>

    <p>
        Check whether the META key is
        pressed or not
    </p> 

    <input type="text" onkeydown="keyboard(event)">

    <p id="test"></p>

    <!-- script to ckeck meta key pressed or not -->
    <script>
        function keyboard(event) {
            var a = document.getElementById("test");
            if (event.metaKey) {
                a.innerHTML = "The META key has been pressed!";
            } 
            else {
                a.innerHTML = "The META key has not been pressed!";
            }
        }
    </script>
</body>

</html>                                                
```

**输出:**
**按键前:**
![](img/3d94dbafdfbb8ee052936f850d3d85d9.png)
**按键后:**
![](img/5d42521489e29da93f959a38b141fab9.png)

**支持的网络浏览器**

*   歌剧
*   微软公司出品的 web 浏览器
*   谷歌 Chrome
*   火狐浏览器
*   苹果 Safari