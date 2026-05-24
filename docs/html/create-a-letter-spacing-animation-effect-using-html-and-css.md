# 使用 HTML 和 CSS 创建字母间距动画效果

> 原文:[https://www . geesforgeks . org/create-a-字母-间距-动画-效果-使用-html-and-css/](https://www.geeksforgeeks.org/create-a-letter-spacing-animation-effect-using-html-and-css/)

在本文中，我们将使用 [CSS](https://www.geeksforgeeks.org/css-tutorials/) 创建一个字母间距动画。字母间距是特定单词中字母之间的可用空间，我们将通过每一步来为我们的网页实现这种动画效果。

**进场:**

*   最初，字母间距为-15px。
*   20%时，字母间距为 10px。
*   最后，100%的字母间距将是 2px。

**示例:**在本例中，我们将动画显示单词的字母间距。我们使用了 [*动画*](https://www.geeksforgeeks.org/css-animation-and-keyframes-property/) 属性，该属性用于在 CSS 中创建动画。我们设置了 3 秒的持续时间。我们必须使用[@关键帧规则](https://www.geeksforgeeks.org/css-animation-and-keyframes-property/)，它们负责使一个元素动画化。我们可以使用百分比值为元素创建动画。在本例中，我们使用三个百分比值作为文本。在我们的例子中，我们将激活字母间距的值，这是 CSS 中文本的一个属性。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>

    <!-- CSS Code -->
    <style>
        * {
            margin: 0;
            padding: 0;
        }

        #text_container {
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            height: 100vh;
        }

        #text {
            font-weight: 100;
            opacity: 1;
            animation: animate 3s ease-out forwards infinite;
            animation-delay: 1s;
        }

        /* For animation */
        @keyframes animate {
            0% {
                letter-spacing: -15px;
            }

            20% {
                letter-spacing: 10px;
            }

            100% {
                letter-spacing: 2px;
            }
        }
    </style>
</head>

<body>
    <div id="text_container">
        <h1 id="text">Geeks for Geeks</h1>
    </div>
</body>

</html>
```

**输出:**

![](img/3bc0aa8ead5c17b9e31878209fa32bf1.png)

字母间距动画