# 如何使用 CSS 将动画绑定到分割元素？

> 原文:[https://www . geeksforgeeks . org/如何使用 css 将动画绑定到分割元素/](https://www.geeksforgeeks.org/how-to-bind-an-animation-to-a-division-element-using-css/)

在本文中，我们将学习使用 CSS 将动画绑定到 div 标签。

一个 [*div*](https://www.geeksforgeeks.org/div-tag-html/) 标签用来分隔网页中内容的不同部分。这使得读者很容易注意到网页的不同部分以及它们在页面上的特定重要性级别。因此，一个 *div* 标签可以用来包含网页的不同部分，也可以根据网页的要求包含文本、图像、动画等。

**方法:**将动画绑定到*分区*标签中必须遵循几个步骤:

*   创建一个包含 [*<头部>*](https://www.geeksforgeeks.org/html-head-tag/)*[*<标题>*](https://www.geeksforgeeks.org/html-title-tag/)*[*<正文>*](https://www.geeksforgeeks.org/html-body-tag/) 元素的基本 HTML 页面。**
*   **创建一个具有特定类名的容器，并添加另一个容器，该容器将包含其中的 HTML 文档的动画部分。这是在 HTML 文档的 *<正文>* 部分创建的。**
*   **确保包含类名的 *< div >* 标签必须与 CSS 属性中的类名匹配。**

****示例:**以下示例演示了使用 [CSS](https://www.geeksforgeeks.org/css-tutorials/) 将动画绑定到分割元素。**

## **超文本标记语言**

```html
**<!DOCTYPE html>
<html>
  <body>
    <div class="gfg">
      <p>GeeksforGeeks</p>
      <div class="circle_1"></div>
    </div>
    <style type="text/css">
      .gfg {
        color: green;
        float: center;
        margin-right: 2%;
        font-size: 60px;
      }

      .circle_1 {
        display: block;
        width: 100px;
        height: 100px;
        background: #056608;
        border-radius: 50%;
        background: -webkit-radial-gradient(25px 25px, circle, #228b22, #000);
        background: -moz-radial-gradient(25px 25px, circle, #228b22, #000);
        background: radial-gradient(25px 25px, circle, #228b22, #000);

        /* Animation to spin and move the sphere */
        -webkit-animation: spin 1000ms linear infinite,
          moveLeftToRight 5s linear infinite;
        -moz-animation: spin 1000ms linear infinite,
          moveLeftToRight 5s linear infinite;
        -ms-animation: spin 1000ms linear infinite,
          moveLeftToRight 5s linear infinite;
        animation: spin 1000ms linear infinite,
          moveLeftToRight 5s linear infinite;

        -webkit-transition: all 1s ease;
        transition: all 1s ease;

        position: absolute;
        left: 0;
      }

      /* Spinning the sphere using key frames */
      @-ms-keyframes spin {
        from {
          -ms-transform: rotate(0deg);
        }
        to {
          -ms-transform: rotate(360deg);
        }
      }
      @-moz-keyframes spin {
        from {
          -moz-transform: rotate(0deg);
        }
        to {
          -moz-transform: rotate(360deg);
        }
      }
      @keyframes spin {
        from {
          transform: rotate(0deg);
        }
        to {
          transform: rotate(360deg);
        }
      }
      @-webkit-keyframes spin {
        from {
          -webkit-transform: rotate(0deg);
        }
        to {
          -webkit-transform: rotate(360deg);
        }
      }

      /* Move sphere from left to right */
      @-moz-keyframes moveLeftToRight {
        0% {
          left: -100px;
        }
        100% {
          left: 100%;
        }
      }
      @-ms-keyframes moveLeftToRight {
        0% {
          left: -100px;
        }
        100% {
          left: 100%;
        }
      }
      @keyframes moveLeftToRight {
        0% {
          left: -100px;
        }
        100% {
          left: 100%;
        }
      }
      @-webkit-keyframes moveLeftToRight {
        0% {
          left: -100px;
        }
        100% {
          left: 100%;
        }
      }
    </style>
  </body>
</html>**
```

****输出:****

**![](img/2385c9fb974b703a3ddbf24619c7dfaa.png)**