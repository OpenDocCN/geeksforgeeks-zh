# 使用 CSS 的双层文字效果

> 原文:[https://www . geesforgeks . org/双层-文本-效果-使用-css/](https://www.geeksforgeeks.org/double-layered-text-effect-using-css/)

在以动画网站及其用户为受众的文本动画世界中，双层文本效果功能是非常新的。该功能基本上每个单词有两层，上层可以通过**悬停**等各种事件进行操作。上层的旋转是以一定的角度进行的，以产生一种铰链的效果。看起来上层从一个点铰接到下层。

**方法:**方法是首先使用选择器之前的[创建两个图层，然后使用](https://www.geeksforgeeks.org/css-before-selector/)[悬停](https://www.geeksforgeeks.org/css-hover-selector/)选择器在鼠标悬停时旋转它。

**HTML 代码:**在这一节中，我们将每个字母表包装在一个跨度中，数据标题属性的值与字母表的值相同。

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content=
        "width=device-width, initial-scale=1.0" />
    <title>Double Layered Text</title>
<body>
    <div class="geeks">
      <span data-title="G">G</span>
      <span data-title="E">E</span>
      <span data-title="E">E</span>
      <span data-title="K">K</span>
      <span data-title="S">S</span>
      <span data-title="F">F</span>
      <span data-title="O">O</span>
      <span data-title="R">R</span>
      <span data-title="G">G</span>
      <span data-title="E">E</span>
      <span data-title="E">E</span>
      <span data-title="K">K</span>
      <span data-title="S">S</span>
    </div>
</body>

</html>
```

**CSS 代码:**

*   **步骤 1:** 执行一些基本的样式，如背景、字体系列、字体大小和将文本调整到中心。
*   **步骤 2:** 现在使用之前的*选择器，内容设置为*跨度*标签中使用的*数据标题*。这将创建文本的第二层。确保提供与第一层不同的颜色。*
*   **第三步:**现在使用一些过渡来给出平滑的动画。
*   **第四步:**最后用*悬停*选择器改变视角或者简单的说旋转第二层。

**注意:**仔细选择您的角度旋转和过渡值。您可以使用浏览器控制台来获得完美的值。

```html
<style>
    body {
        background: black;
    }

    .geeks {
        text-align: center;
        margin: 200px auto 0;
        font-family: Arial, Helvetica, sans-serif;

    }

    .geeks span {
        font-size: 80px;
        font-weight: 700;
        color: green;
        position: relative;
        text-shadow: -1px 0 0 rgba(0, 0, 0, .2);
    }

    .geeks span::before {
        content: attr(data-title);
        position: absolute;
        top: 0;
        left: 0;
        transform-origin: left;
        color: #fff;
        transition: .5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        transform: rotateY(25deg);
    }

    .geeks span:hover::before {
        transform: perspective(1000px) rotate(-67deg);
    }
</style>
```

**完整代码:**是上面两段代码的组合。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content=
        "width=device-width, initial-scale=1.0" />

    <title>Double Layered Text</title>

    <style>
        body {
            background: black;
        }

        .geeks {
            text-align: center;
            margin: 200px auto 0;
            font-family: Arial, Helvetica, sans-serif;
        }

        .geeks span {
            font-size: 80px;
            font-weight: 700;
            color: green;
            position: relative;
            text-shadow: -1px 0 0 rgba(0, 0, 0, .2);
        }

        .geeks span::before {
            content: attr(data-title);
            position: absolute;
            top: 0;
            left: 0;
            transform-origin: left;
            color: #fff;
            transition: .5s cubic-bezier(
                0.175, 0.885, 0.32, 1.275);
            transform: rotateY(25deg);
        }

        .geeks span:hover::before {
            transform: perspective(1000px) rotate(-67deg);
        }
    </style>
</head>

<body>
    <div class="geeks">
        <span data-title="G">G</span>
        <span data-title="E">E</span>
        <span data-title="E">E</span>
        <span data-title="K">K</span>
        <span data-title="S">S</span>
        <span data-title="F">F</span>
        <span data-title="O">O</span>
        <span data-title="R">R</span>
        <span data-title="G">G</span>
        <span data-title="E">E</span>
        <span data-title="E">E</span>
        <span data-title="K">K</span>
        <span data-title="S">S</span>
    </div>
</body>

</html>
```

**输出:**
![](img/0d173d4f29b28ce994f64fc62f514bcf.png)