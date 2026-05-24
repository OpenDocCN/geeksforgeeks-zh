# 使用 CSS3

淡化文本动画效果

> 原文:[https://www . geesforgeks . org/fading-text-animation-effect-using-css3/](https://www.geeksforgeeks.org/fading-text-animation-effect-using-css3/)

渐弱的文本动画效果是用户界面/UX 设计中要求最高的效果之一。这种效果可以通过使用 HTML5 和 CSS3 来实现。在淡入淡出的文字效果中，每当我们加载窗口时，文字就会慢慢开始消失。我们可以使用 CSS3 中的动画属性来实现这种效果。

**HTML 代码:**在本节中，我们将制作网页的布局。

*   **index.html**

## 超文本标记语言

```html
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content=
        "width=device-width, initial-scale=1.0">
</head>

<body>
    <div>
        <h2>GeeksforGeeks</h2>
    </div>
</body>

</html>
```

**CSS 代码:**在本节中，我们将添加一些 CSS 属性来创建一个淡入淡出的文本效果。

## 半铸钢ˌ钢性铸铁(Cast Semi-Steel)

```html
<style>
    * {
        margin: 0;
        padding: 0;

    }

    body {
        display: flex;
        justify-content: center;
        align-items: center;
        min-height: 100vh;
        background: green;
        animation-name: gfg;
        animation-duration: 4s;
    }

    h2 {
        position: relative;
        margin: 0;
        font-size: 5em;
        font-weight: 750;
        color: white;
        z-index: 1;
        overflow: hidden;
    }

    h2:before {
        content: '';
        position: absolute;
        right: 130%;
        width: 130%;
        height: 100%;
        background: linear-gradient(90deg, 
            transparent 0%, green 5%, green 100%);

        animation: geeksforgeeks 5s linear backwards;
    }

    @keyframes geeksforgeeks {
        from {
            right: 130%
        }

        to {
            right: -10%;
        }
    }
</style>
```

**完整代码:**在本节中，我们将结合以上两个部分，使用 HTML5 和 CSS3 创建一个淡入淡出的文本效果。

## 超文本标记语言

```html
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content=
        "width=device-width, initial-scale=1.0">

    <style>
        * {
            margin: 0;
            padding: 0;

        }

        body {
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            background: green;
            animation-name: gfg;
            animation-duration: 4s;
        }

        h2 {
            position: relative;
            margin: 0;
            font-size: 5em;
            font-weight: 750;
            color: white;
            z-index: 1;
            overflow: hidden;
        }

        h2:before {
            content: '';
            position: absolute;
            right: 130%;
            width: 130%;
            height: 100%;
            background: linear-gradient(90deg, 
                transparent 0%, green 5%, green 100%);

            animation: geeksforgeeks 5s linear backwards;
        }

        @keyframes geeksforgeeks {
            from {
                right: 130%
            }

            to {
                right: -10%;
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

![](img/9e43c678f81f2dafaccb54ee807aa814.png)