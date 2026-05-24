# 如何使用 HTML 和 CSS 创建文字颜色动画？

> 原文:[https://www . geesforgeks . org/how-create-text-color-animation-use-html-and-CSS/](https://www.geeksforgeeks.org/how-to-create-text-color-animation-using-html-and-css/)

使用 CSS**@关键帧**规则，可以根据程序员的选择改变文本颜色。

**HTML 代码:**下面的代码片段创建了包含要修改的文本的 HTML em div 元素。

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content=
    "width=device-width, initial-scale=1.0">
  <title>Text Color Animation</title>
</head>
<body>
  <div>
    <h2>GeeksforGeeks</h2>
  </div>
</body>
</html>
```

**CSS 代码:**下面的代码片段演示了文本的设计，使用了一些基本的 CSS 属性以及 CSS**@关键帧**规则来改变文本的颜色以产生动画效果。

```html
<style>
    body {
        margin: 0;
        padding: 0;
    }

    div {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
    }

    h2 {
        font-size: 5em;
        font-family: serif;
        color: transparent;
        text-align: center;
        animation: effect 2s linear infinite;
    }

    @keyframes effect {
        0% {
            background: linear-gradient(
                #008000, #00FF00);
            -webkit-background-clip: text;
        }

        100% {
            background: linear-gradient(
                #3CE7D7, #000FFF);
            -webkit-background-clip: text;
        }
    }
</style>
```

**完整代码:**是以上两个代码段的组合。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content=
        "width=device-width, initial-scale=1.0">
    <title>Text Color Animation</title>

    <style>
        body {
            margin: 0;
            padding: 0;
        }

        div {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
        }

        h2 {
            font-size: 5em;
            font-family: serif;
            color: transparent;
            text-align: center;
            animation: effect 2s linear infinite;
            \
        }

        @keyframes effect {
            0% {
                background: linear-gradient(
                        #008000, #00FF00);
                -webkit-background-clip: text;
            }

            100% {
                background: linear-gradient(
                        #3CE7D7, #000FFF);
                -webkit-background-clip: text;
            }
        }
    </style>
</head>

<body>
    <div>
        <h2>GeeksforGeeks</h2>
    </div>
</body>

</html>
```

**输出:**
![](img/0bd10d5d8775b3c05d77765e8560dfe8.png)