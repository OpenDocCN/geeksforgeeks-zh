# 如何在 CSS 中定义一个动画需要多长时间才能完成？

> 原文:[https://www . geeksforgeeks . org/如何定义 css 中动画需要多长时间才能完成/](https://www.geeksforgeeks.org/how-to-define-the-duration-of-an-animation-takes-to-complete-in-css/)

设计网站时，通常使用 [JavaScript](https://www.geeksforgeeks.org/introduction-to-javascript/) 来定义网页的行为。但是有一些方法可以帮助我们使用 CSS 定义页面的某些行为。其中一个行为就是动画。CSS 动画是帮助我们在不使用 JavaScript 的情况下改变网页行为和外观的方法。它们为不同的时间间隔定义元素的外观，从而显示动画。

**定义动画持续时间:**要使用 CSS 动画，我们需要定义 CSS 显示不同外观的时间间隔。为此，我们有**动画-持续时间**属性，该属性设置动画完成一个周期所需的时间间隔。

**语法:**

```html
animation-duration: (time in seconds);
```

以下是说明使用*动画-持续时间的例子。*

**示例:**我们现在将创建一个变色动画。让我们首先创建我们的 HTML 文件，它将包含我们想要应用动画的文本。

## index.html

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
  <head>
    <meta charset="utf-8">
    <title>Animation example</title>
    <!-- This line defines the css styles file to be used -->
    <link rel="stylesheet" href="css/style.css">
  </head>
  <body>
    <h1 id="mainh1">GeeksforGeeks</h1>
  </body>
</html>
```

现在我们的 HTML 文件已经准备好了，我们可以在 CSS 文件中定义我们的样式和动画。在这个例子中，我们将使用**动画-持续时间**属性，它将在 5 秒内改变我们标题的颜色。

**CSS 代码:**注意，我们在这里创建了一个名为‘change’的自定义动画。要了解如何创建 CSS 动画，请参考这篇[文章](https://www.geeksforgeeks.org/css-animations/)。

这里要注意的主要事情是，我们已经将动画的持续时间定义为 5 秒。这意味着标题的文本颜色应该在 5 秒钟内从绿色变为红色。

## style.css

```html
#mainh1{
  animation-name: change;
  animation-duration: 5s;
  animation-iteration-count: infinite;
}

@keyframes change {
  from {
    color: green;
  }
  to {
    color: red;
  }
}
```

**完整代码:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">

<head>
  <style>
    #mainh1{
      animation-name: change;
      animation-duration: 5s;
      animation-iteration-count: infinite;
    }

    @keyframes change {
      from {
        color: green;
      }
      to {
        color: red;
      }
    }
  </style>
</head>

<body>
  <h1 id="mainh1">
    GeeksforGeeks
  </h1>
</body>

</html>
```

**输出:**

![](img/9defbb94660d687bfaca4f3755c006bb.png)