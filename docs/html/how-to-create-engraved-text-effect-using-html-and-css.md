# 如何使用 HTML 和 CSS 创建刻文效果？

> 原文:[https://www . geesforgeks . org/如何使用 html 和 css 创建雕刻文本效果/](https://www.geeksforgeeks.org/how-to-create-engraved-text-effect-using-html-and-css/)

雕刻文本效果是一种效果，您可以在网站中将其用作标题或子标题，以使其看起来更加令人愉悦和吸引人。

**方法:**使用 HTML 和 CSS 很容易生成雕刻的文字效果。首先，我们将使用 HTML 创建一个基本文本，然后通过使用 CSS **[文本-阴影](https://www.geeksforgeeks.org/css-text-shadow-property/)** 属性，我们将生成所需的效果。

**例 1:**

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">

<head>
    <meta charset="utf-8">
    <title>Engraved Text Effect</title>
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
            color: transparent;
            background: #008000;
            -webkit-background-clip: text;
            text-shadow: 2px 5px 5px 
                rgba(255, 255, 255, 0.3);
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

在上面的例子中，我们首先创建一个包含一些文本的 **div** 标签，然后我们使用 CSS 基本属性设计文本。然后我们将使用**文本-阴影**属性来生成雕刻效果。

**输出:**
![](img/b607205622ebb2451b0159d800a71b22.png)

**例 2:**

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">

<head>
    <meta charset="utf-8">
    <title>Engraved Text Effect</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            font-family: serif;
            justify-content: center;
            align-items: center;
            display: flex;
            background-color: gray;
        }

        div {
            content: '';
            font-size: 3em;
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-70%, -90%);
            color: transparent;
            background: black;
            -webkit-background-clip: text;
            text-shadow: 2px 5px 5px 
                rgba(255, 255, 255, 0.3);
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
![](img/e914b3076cd1a68b343f32ee8900f398.png)