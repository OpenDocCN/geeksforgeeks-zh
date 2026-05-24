# 如何使用 CSS 创建浮雕文字效果？

> 原文:[https://www . geesforgeks . org/how-create-浮雕-文字-效果-使用-css/](https://www.geeksforgeeks.org/how-to-create-embossed-text-effect-using-css/)

使用 HTML 和 CSS 可以轻松生成浮雕文本效果。我们将使用 CSS **文本阴影**属性来获得想要的输出。

**HTML 代码:**在本节中，我们将创建一个容纳文本或标题的正文的基本结构。

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">

<head>
    <meta charset="utf-8">
    <title>Embossed Text Effect</title>
</head>

<body>
    <div>
        <h2>GeeksforGeeks</h2>
    </div>
</body>

</html>
```

**CSS 代码:**在本节中，我们将对文本进行样式化。我们将使用 CSS **文本-阴影**属性为文本添加阴影并创建浮雕效果。

```html
<style>
    body {
        margin: 0;
        padding: 0;
        font-family: serif;
        justify-content: center;
        align-items: center;
        display: flex;
        background-color: #65E73C;
    }

    div {
        content: '';
        font-size: 3em;
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
    }

    h2 {
        color: #65E73C;
        text-shadow: -2px 2px 4px 
            rgba(0, 0, 0, 0.5), 
            2px -2px 0 
            rgba(255, 255, 255, 0.9);
    }
</style>
```

**最终代码:**是以上两个代码段的组合。

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">

<head>
    <meta charset="utf-8">
    <title>Embossed Text Effect</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            font-family: serif;
            justify-content: center;
            align-items: center;
            display: flex;
            background-color: #65E73C;
        }

        div {
            content: '';
            font-size: 3em;
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
        }

        h2 {
            color: #65E73C;
            text-shadow: -2px 2px 4px rgba(0, 0, 0, 0.5),
                2px -2px 0 rgba(255, 255, 255, 0.9);
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
![](img/c6716283c5872b8c484f17f684927cfb.png)