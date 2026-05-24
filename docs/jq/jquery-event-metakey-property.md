# jQuery event.metaKey 属性

> 原文:[https://www . geesforgeks . org/jquery-event-meta key-property/](https://www.geeksforgeeks.org/jquery-event-metakey-property/)

jQuery 中的**事件元键**属性用于识别元键是否被按下。下面讨论两个例子。
**语法:**

```html
event.metaKey
```

**返回值:**如果密钥是元密钥，则返回“真”，否则返回“假”。

**示例 1:** 在本示例中，键入<输入>元素并查看结果。

```html
<!DOCTYPE HTML>
<html>

<head>
    <title>
        jQuery event.metaKey Property
    </title>

    <script src=
"https://code.jquery.com/jquery-3.5.0.js">
    </script>
</head>

<body style="text-align:center;">

    <h1 style="color:green;">
        GeeksForGeeks
    </h1>

    <p id="GFG_UP"></p>

    <input type="text" 
        onkeydown="Geeks(event)" />

    <p id="GFG_DOWN"></p>

    <script>
        var elUp = document.getElementById("GFG_UP");
        var elDown = document.getElementById("GFG_DOWN");
        elUp.innerHTML = "JQuery | event.metaKey property";

        function Geeks(event) {
            if (event.metaKey) {
                elDown.innerHTML = 
                    "The META key was pressed!";
            } else {
                elDown.innerHTML = 
                    "The META key was NOT pressed!";
            }
        } 
    </script>
</body>

</html>
```

**输出:**
![](img/e262455548d73861eb0d656930e452f9.png)

**示例 2:** 从文档中的任意位置按下任意按钮，查看结果。

```html
<!DOCTYPE HTML>
<html>

<head>
    <title>
        JQuery event.metaKey Property
    </title>

    <script src=
"https://code.jquery.com/jquery-3.5.0.js">
    </script>
</head>

<body style="text-align:center;">

    <h1 style="color:green;">
        GeeksForGeeks
    </h1>

    <p id="GFG_UP"></p>

    <p id="GFG_DOWN"></p>

    <script>
        var elUp = document.getElementById("GFG_UP");
        var elDown = document.getElementById("GFG_DOWN");
        elUp.innerHTML = "JQuery | event.metaKey property";

        $('html').click(function (event) {
            if (event.metaKey) {
                elDown.innerHTML = 
                    "The META key was pressed!";
            } else {
                elDown.innerHTML = 
                    "The META key was NOT pressed!";
            }
        }); 
    </script>
</body>

</html>
```

**输出:**
![](img/9500a6538da3bbdade61aef2662f8b79.png)