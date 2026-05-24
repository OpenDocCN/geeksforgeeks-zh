# 如何使用 HTML 和 CSS 创建反射效果？

> 原文:[https://www . geesforgeks . org/how-create-reflection-effect-use-html-and-CSS/](https://www.geeksforgeeks.org/how-to-create-reflection-effect-using-html-and-css/)

反射效果是一个人可以在他/她的网站上使用的最酷的效果之一。这是一种非正式的效果，所以强烈建议不要在任何专业项目中使用。你可以在你的个人项目中使用它，也可以在你的投资组合中展示你的创造力。在这种效果中，我们试图模仿一种逼真的反射效果，就像它从水中反射一样。

**方法:**方法是在原始字符串的底部创建一个旋转的字符串，然后改变其不透明度和背景，使其看起来像原始字符串的反射。让我们看看上述方法的实施情况。

**HTML 代码:**在本节中，创建了“h2”标签，其中包含了文本。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content=
        "width=device-width, 
        initial-scale=1.0" />

    <title>
        Text Reflection 
        using HTML and CSS
    </title>
</head>

<body>
    <h2 data-text="GeeksforGeeks">
        GeeksforGeeks
    </h2>
</body>

</html>
```

**CSS 代码:**

*   **第一步:**应用一个中心较亮，角落较暗的放射状背景。
*   **第二步:**在标题上应用一些基本的样式，如大小、颜色等。
*   **第三步:**现在使用选择器后的[，在 X 轴上旋转原始文本，保持原点为底部。](https://www.geeksforgeeks.org/css-after-selector/)
*   **第 4 步:**应用“webkit”属性将旋转后的文本剪切成多个剪切块。它将使文本的上部
    部分可见，如输出图像所示。
*   **第五步:**现在应用透明颜色，降低旋转文本的不透明度。

**注意:**确保根据你的背景降低不透明度。如果你使用的是较暗的
背景，降低不透明度 0.1-0.2，如果你使用的是较亮的背景，则降低 0.6-0.8。

```html
<style>
 body 
     {
       /* Radiel gradient defined by its center*/
        background-image: radial-gradient(#013220,#008000);
        height: 100vh;
      }

      h2 {
        position: absolute;
        top: 30%;
        left: 30%;
        text-transform: capitalize;
        color: white;
        font-size: 50px;
      }
      h2::after {
        content: attr(data-text);
        position: absolute;
        top: 0;
        left: 0;
    /* Change the position of transformed element */
        transform-origin: bottom;
    /*  Rotates around x-axis */
        transform: rotateX(180deg);
        line-height: 0.85em;
    /* linear-gradient defined by up,down,left ,right ,diagonal */
        background-image: linear-gradient(0deg, #ffffff 0, transparent 95%);
        -webkit-background-clip: text;
        color: transparent;         
        opacity: 0.7;
      }
  </style>
```

**完整代码:**是以上两段代码的组合。

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Text Reflection using HTML and CSS</title>
    <style>
      body 
     {
       /* Radiel gradient defined by its center*/
        background-image: radial-gradient(#013220,#008000);
        height: 100vh;
      }

      h2 {
        position: absolute;
        top: 30%;
        left: 30%;
        text-transform: capitalize;
        color: white;
        font-size: 50px;
      }
      h2::after {
        content: attr(data-text);
        position: absolute;
        top: 0;
        left: 0;
    /* Change the position of transformed element */
        transform-origin: bottom;
    /*  Rotates around x-axis */
        transform: rotateX(180deg);
        line-height: 0.85em;
    /* linear-gradient defined by up,down,left ,right ,diagonal */
        background-image: linear-gradient(0deg, #ffffff 0, transparent 95%);
        -webkit-background-clip: text;
        color: transparent;         
        opacity: 0.7;
      }
    </style>
  </head>
  <body>
    <h2 data-text="GeeksforGeeks">GeeksforGeeks</h2>
  </body>
</html>
```

**输出:**
![](img/45f7c24d6d273d45601cf8844cd451e6.png)