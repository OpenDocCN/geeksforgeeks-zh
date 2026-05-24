# 使用 HTML 和 CSS 创建渐变文本效果

> 原文:[https://www . geesforgeks . org/create-a-gradient-text-effect-using-html-and-CSS/](https://www.geeksforgeeks.org/create-a-gradient-text-effect-using-html-and-css/)

本文将展示使用背景剪辑 CSS 属性在文本上添加渐变效果的方法。使用这种效果的文本的最终输出如下所示。将使用的 CSS 属性是 **flexbox** 、**背景剪辑**、**网络工具包-背景剪辑**和**背景**。

**HTML 部分:**该部分包含 HTML 标记，该标记将包含需要设置样式的文本。作为一种良好的做法，文本被包装在容器 div 中，以帮助它在页面上居中。类渐变也被添加到文本中。这一节不需要更复杂的内容。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>CSS Text Gradient</title>
</head>

<body>
    <div class="container">
        <h1 class="gradient">
            Happy Halloween
        </h1>
    </div>
</body>

</html>
```

**CSS 部分:**CSS 部分将包括使用渐变效果设置文本的样式。一个名为*金属狂热*的谷歌字体被用来给它想要的效果。作为一种良好的做法，我们将首先重置 CSS 中的所有内容。将要使用的谷歌字体将被导入并在接下来使用。我们还将使用 flexbox 属性来集中所有内容。

## 半铸钢ˌ钢性铸铁(Cast Semi-Steel)

```html
<style>
    @import url(
"https://fonts.googleapis.com/css2?family=Metal+Mania&display=swap");

    * {
        box-sizing: border-box;
        margin: 0;
        padding: 0;
    }

    body {
        font-family: "Metal Mania",
            cursive;
    }

    .container {
        background: #000;
        height: 100vh;

        /* Center everything in the page */
        display: flex;
        justify-content: center;
        align-items: center;
    }
</style>
```

**创建渐变效果:**我们将开始制作主渐变效果。逻辑是为文本设置线性渐变背景。然后背景被剪裁成文本的大小。剪切后，文本颜色设置为透明。

**内嵌块**属性将背景设为标题文本的大小。带有**文本**值的**背景剪辑**属性将允许我们将线性渐变背景剪辑到文本。 **-webkit** 前缀版本用于使其故障安全。使文本颜色透明只会显示**线性渐变**背景。

## 半铸钢ˌ钢性铸铁(Cast Semi-Steel)

```html
<style>
    .gradient {
        font-size: 5rem;

        /* Set the background of
        the text  */
        background:
            linear-gradient(to right,
                #fcc133,
                #334efc);
        display: inline-block;

        /* Clip the background upto
        the text  */
        -webkit-background-clip: text;
        background-clip: text;

        /* Set the color of the text
        to transparent  */
        color: transparent;
    }
</style>
```

**完整代码:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>CSS Text Gradient</title>

    <style>
        @import url(
"https://fonts.googleapis.com/css2?family=Metal+Mania&display=swap");

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: "Metal Mania",
                cursive;
        }

        .container {
            background: #000;
            height: 100vh;

            /* Center everything in the page */
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .gradient {
            font-size: 5rem;

            /* Set the background of 
                the text  */
            background:
                linear-gradient(to right,
                    #fcc133,
                    #334efc);
            display: inline-block;

            /* Clip the background upto
                the text  */
            -webkit-background-clip: text;
            background-clip: text;

            /* Set the color of the text
                to transparent  */
            color: transparent;
        }
    </style>
</head>

<body>
    <div class="container">
        <h1 class="gradient">
            Happy Halloween
        </h1>
    </div>
</body>

</html>
```

**输出:**

![](img/471968992714dc5262ed18d5ff363fd1.png)