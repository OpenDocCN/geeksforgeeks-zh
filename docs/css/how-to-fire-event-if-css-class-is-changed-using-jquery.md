# 如果使用 jQuery 改变 CSS 类，如何触发事件？

> 原文:[https://www . geesforgeks . org/how-fire-event-if-CSS-class-is-changed-use-jquery/](https://www.geeksforgeeks.org/how-to-fire-event-if-css-class-is-changed-using-jquery/)

给定一个带有标题和按钮的 HTML 文档，当按钮的 CSS 类改变时，jQuery 应该触发一个事件。

**方法:**在 jQuery 中，没有关于类变化触发事件的规定。另一种方法是，当您使用 [**触发器()**函数](https://www.geeksforgeeks.org/jquery-trigger-method/)以编程方式更改类时，手动引发事件。每当按钮的等级改变时，**触发器()**功能将引发一个事件。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>

    <meta charset="UTF-8">
    <meta name="viewport" content=
        "width=device-width, initial-scale=1.0">

    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.4.0/jquery.min.js">
    </script>

    <style>
        .buttonstyle {
            background-color: #4CB96B;
            color: white;
        }

        .buttonsize {
            padding: 1em;
            height: 70px;
            width: 400px;
            border: .5px solid black;
            outline: none;
            font-size: large;
            border-radius: 10px;
        }
    </style>
</head>

<body>
    <center>
        <h1>
            Click the button to
            change its style
        </h1>

        <button id="classchange-btn" 
            class="buttonsize">
            Click Me
        </button>
    </center>

    <script>
        $("#classchange-btn").click(function () {
            $(this).toggleClass("buttonstyle")
                    .trigger('classChanged');
        });

        $("#classchange-btn").on(
            "classChanged", function () {
            alert("Button Style Change event fired");
        });
    </script>
</body>

</html>
```

**Output:**
![](img/c369cb6b18e5058b125904de1c92f874.png)

最初页面看起来像下图。

![](img/2721fa18a614bcdedbd119aedf3e89c5.png)

单击按钮时，会弹出一条警告消息，指示侦听器已被激发，并且按钮的 CSS 类已更改。

![](img/5c60dcbb5680fd52eedacf82a7dcfa37.png)

关闭弹出窗口后，按钮的 CSS 类发生了变化(注意绿色背景颜色和白色文本)。

jQuery 是一个开源的 JavaScript 库，它简化了 HTML/CSS 文档之间的交互，它以其“少写多做”的理念而闻名。
跟随本 [jQuery 教程](https://www.geeksforgeeks.org/jquery-tutorials/)和 [jQuery 示例](https://www.geeksforgeeks.org/jquery-examples/)可以从头开始学习 jQuery。