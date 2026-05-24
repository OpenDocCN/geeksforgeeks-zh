# 如何使用 HTML 和 CSS 创建打字机动画？

> 原文:[https://www . geeksforgeeks . org/如何创建-打字机-动画-使用-html-and-css/](https://www.geeksforgeeks.org/how-to-create-typewriter-animation-using-html-and-css/)

**打字机动画**顾名思义就是一种看起来像打字动画的效果，就像是被打字机打出来的一样。我们将创建这个没有 JavaScript 的动画，只使用 HTML 和 CSS。

**方法:**为了实现打字机效果，我们将使用以下 CSS 属性。

*   [**动画-计时-功能**](https://www.geeksforgeeks.org/css-animation-timing-function-property/#:~:text=The%20animation%2Dtiming%2Dfunction%20property,motion%20of%20animation%20during%20transitions.)【T4:我们需要指定动画的时间，以秒或毫秒为单位，这样动画更快，看起来更完美。我们还需要指定步骤，这样每个字母就不会像在打字机上看到的那样一个接一个地出现。在下面的代码中，我们使用了 geesforgeks 示例，因为 geesforgeks 中的字母总数是 13，所以使用的步骤数是 13。
*   [**溢出**](https://www.geeksforgeeks.org/css-overflow/#:~:text=The%20CSS%20overflow%20controls%20big,or%20to%20add%20scroll%20bars.&text=Output%3A,of%20the%20content%20is%20invisible.) **:** 这样每个文字都按照动画出现，不会一下子全部显露出来，**溢出:隐藏**用在下面的代码中。
*   [](https://www.geeksforgeeks.org/css-white-space-property/#:~:text=Property%20Values%3A,element%20will%20wrap%20wherever%20necessary.)****:**要在一条线上获得动画**需要使用空格:nowrap** 。**
*   **[**【边框颜色】**](https://www.geeksforgeeks.org/css-border-color-property/) **:** 如下图所示，边框颜色是从黑色设置的，过于透明，无法给动画一种闪烁光标的真实感，除了黑色，任何颜色都可以使用。**
*   **[**宽度**](https://www.geeksforgeeks.org/css-width-property/) **:** 要获得像动画一样的打字宽度，动画宽度从 0%到 50%(这可以根据文本高度/宽度或给定的文本间距而变化)。** 

****示例:**在本例中，我们将使用上面定义的属性来创建打字机动画。**

## **index.htm**

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Typewriter Effect</title>
    <link rel="stylesheet" type="text/css" href="style.css" />
    <style type="text/css">
       {
        box-sizing: border-box;
        padding: 0;
        margin: 0;
        outline: none;
      }
      body {
        background-color: #2ca32c;
        justify-content: center;
        align-items: center;
        height: 100vh;
        display: flex;
      }

      h1 {
        font-size: 90px;
        white-space: nowrap;
        overflow: hidden;
        animation: typewriter 2s steps(13) infinite alternate,
          blink 800ms steps(13) infinite normal;
        border-right: 5px solid black;
      }
      @keyframes typewriter {
        from {
          width: 0%;
        }
        to {
          width: 50%;
        }
      }
      @keyframes blink {
        from {
          border-color: black;
        }
        to {
          border-color: transparent;
        }
      }
    </style>
  </head>
  <body>
    <h1>GeeksforGeeks</h1>
  </body>
</html>
```

****输出:****

**![](img/020d88e83ab99edd617996e3d987981f.png)**

****注意:**对于其他更长或更短的文字，需要在字体大小、步骤上做必要的修改。文本和光标的动画时间也应该相应地改变。**