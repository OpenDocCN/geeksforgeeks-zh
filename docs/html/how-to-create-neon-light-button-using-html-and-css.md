# 如何用 HTML 和 CSS 创建霓虹灯按钮？

> 原文:[https://www . geesforgeks . org/如何使用 html 和 css 创建霓虹灯按钮/](https://www.geeksforgeeks.org/how-to-create-neon-light-button-using-html-and-css/)

霓虹灯按钮动画效果可以通过使用 HTML 和 CSS 轻松生成。通过使用 HTML 我们将设计按钮的基本结构，然后通过使用 CSS 的属性，我们可以创建霓虹灯动画效果。
**HTML 代码:**在本节中，我们将使用[锚点标签](https://www.geeksforgeeks.org/html-a-tag/)设计一个简单的按钮结构。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="utf-8">
    <title>
        How to create Neon Light
        Button using HTML and CSS?
    </title>
</head>

<body>
    <a>GeeksForGeeks</a>
</body>

</html>
```

**CSS 代码:**在本节中，我们将使用一些 CSS 属性来设计按钮，并使用**悬停**类来获得鼠标悬停在按钮上时的动画效果。

## 半铸钢ˌ钢性铸铁(Cast Semi-Steel)

```html
<style>
    /*styling background*/
    body {
        margin: 0;
        padding: 0;
        display: flex;
        height: 100vh;
        justify-content: center;
        align-items: center;
        background-color: #000;
        font-family: sans-serif;
    }

    /* styling the button*/
    a {
        padding: 20px 20px;
        display: inline-block;
        color: #008000;
        letter-spacing: 2px;
        text-transform: uppercase;
        text-decoration: none;
        font-size: 3em;
        overflow: hidden;
    }

    /*creating animation effect*/
    a:hover {
        color: #111;
        background: #39ff14;
        box-shadow: 0 0 50px #39ff14;
    }
</style>
```