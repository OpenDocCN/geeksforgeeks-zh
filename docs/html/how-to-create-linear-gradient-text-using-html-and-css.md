# 如何使用 HTML 和 CSS 创建线性渐变文本？

> 原文:[https://www . geesforgeks . org/如何使用 html 和 css 创建线性渐变文本/](https://www.geeksforgeeks.org/how-to-create-linear-gradient-text-using-html-and-css/)

线性渐变是一种文本样式，其中文本用线性渐变颜色代码填充。这种效果通常用于黑暗主题的网站或应用程序，以使文本看起来有吸引力和大胆。它们几乎适合深色主题，与浅色主题不搭配。

**方法:**请参考[线性渐变()](https://www.geeksforgeeks.org/css-linear-gradient-function/)方法更新渐变背景，然后使用 webkit 属性将该背景与我们的文本叠加。

**HTML 代码:**在下一节中，用于演示的文本被包装在 h1 标签中。

```html
<!-- Write HTML code here -->
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content=
        "width=device-width, 
        initial-scale=1.0" />
    <title>Gradient Text</title>
  </head>
<body>
    <h1>GEEKSFORGEEKS</h1>
  </body>
</html>
```

**CSS 代码:**CSS 代码请按照下面给出的步骤操作。

*   **第 1 步:**在正文标签上应用基本背景，并将文本与页面中心对齐。
*   **第二步:**做一些基本的造型，比如字体大小、家族等。
*   **步骤 3:** 将线性渐变属性应用到您选择的任何颜色。
*   **第四步:**现在应用 webkit 属性，第一个属性将使整个渐变背景透明，第二个属性将使用渐变背景填充文本。

**注意:**你可以给文字加上一些阴影，让它看起来更暗或者是哑光。

```html
<style>
    body {
        background: rgb(39, 39, 39);
    }

    h1 {
        position: absolute;
        top: 40%;
        left: 40%;

        font-size: 40px;
        font-family: Arial, 
            Helvetica, sans-serif;
        background: linear-gradient(
            to right, #f32170, #ff6b08,
             #cf23cf, #eedd44);
        -webkit-text-fill-color: transparent;
        -webkit-background-clip: text;
    }
</style>
```

**完整代码:**是以上两段代码的组合。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content=
        "width=device-width, initial-scale=1.0" />
    <title>Gradient Text</title>
    <style>
        body {
            background: rgb(39, 39, 39);
        }

        h1 {
            position: absolute;
            top: 40%;
            left: 40%;

            font-size: 40px;
            font-family: Arial, Helvetica, sans-serif;
            background: linear-gradient(to right, #f32170,
                    #ff6b08, #cf23cf, #eedd44);
            -webkit-text-fill-color: transparent;
            -webkit-background-clip: text;
        }
    </style>
</head>

<body>
    <h1>GEEKSFORGEEKS</h1>
</body>

</html>
```

**输出:**
![](img/48d06b79b2bf948a9379fa8f17dc4c17.png)