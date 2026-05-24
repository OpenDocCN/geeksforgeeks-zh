# CSS | currentcolor 关键字

> 原文:[https://www.geeksforgeeks.org/css-currentcolor-keyword/](https://www.geeksforgeeks.org/css-currentcolor-keyword/)

CSS **currentcolor** 关键字用于定义颜色，但使用当前使用的颜色属性。如果你想在多个地方使用相同的颜色，那么你可以很容易地使用 **currentcolor** 关键字。只需要设置一个颜色属性，之后你就可以很容易地使用 **currentcolor** 来设置你想要设置的所有其他地方的颜色。所以在未来，如果你想改变所有的颜色，那么你需要在一个地方改变颜色。
**语法:**

```html
background-color: currentcolor;

```

**示例 1:** 在本例中，我们将使用 currentcolor 进行框阴影。

```html
<!DOCTYPE html>
<html>
<head>
    <title>
        CSS currentcolor keyword
    </title>
    <style>
        body {
            color: green;
            font-size: 1.2em;
        }

        div {
            box-shadow: 0px 0px 80px currentcolor;
            border: 10px solid;
            width: 50%;
            margin: auto;
            padding: 20px;
        }
    </style>
</head>

<body>
    <center>
        <h1>GeeksforGeeks</h1>

        <div>
            A Computer Science Portal
        </div>
    </center>
</body>
</html>
```

**输出:**
![](img/cc3b03fc096bc0a482b03b38446d4be9.png)

**示例 2:** 当前颜色背景上的文本颜色。

```html
<!DOCTYPE html>
<html>
<title>CSS currentcolor keyword</title>

<head>
    <style>
        body {
            color: green;
        }

        div {
            background: currentcolor;
            width: 60%;
            margin: auto;
            padding: 5px 20px;
        }

        div > p {
            color: white;
            opacity: 0.5;
            font-size: 1.5em;
        }
    </style>
</head>

<body>
    <center>
        <h1>GeeksforGeeks</h1>
        <div>
            <p>A Computer Science Portal</p>
        </div>
    </center>
</body>

</html>
```

**输出:**
![](img/19adc469bc180b4ff967227363d744d2.png)

**支持的浏览器:**CSS current color 关键字支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队