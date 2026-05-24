# 如何使用 HTML 和 CSS 创建动画条？

> 原文:[https://www . geeksforgeeks . org/如何使用 html 和 css 创建动画条/](https://www.geeksforgeeks.org/how-to-create-animated-bars-using-html-and-css/)

跳舞吧是制作一个好看的网站的经典组成部分之一。它们实现起来非常简单，可以在录音时用作加载器或动画。

**方法:**方法是使用无序列表创建条，然后使用关键帧对其进行动画制作。在本文继续之前，您应该了解 CSS 的关键帧和第 n 个子属性。

**HTML 代码:**在本节中，我们创建了一个无序列表。

```html
<!DOCTYPE html>
<html>
<head>
<title>Dancing Bars</title>
</head>
<body>
  <ul>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
  </ul>
</body>
</html>
```

**CSS 代码:**对于 CSS，请按照以下步骤操作:

*   **第 1 步:**将 ul 与页面中心对齐。
*   **第二步:**去掉列表的所有样式，应用一些宽度和高度，做成条状。
*   **第 3 步:**使用关键帧沿 Y 轴设置条的动画。为此，请增加最后一帧的比例。
*   **步骤 4:** 使用第 n 个子属性在每个 li 元素之间应用. 1s 延迟。

**提示:**你也可以使用 scaleX 在水平视图中进行同样的设计，并保持列表的默认排列。

```html
ul{
      position: absolute;
      top:50%;
      left:50%;
      display: flex;
    }
    ul li{
      list-style: none;
      width: 6px;
      height: 20px;
      background: #262626;
      margin: 0 4px;
      animation: animate .7s infinite alternate 
      }
      @keyframes animate {
        0%{
          transform: scaleY(1);
        }
         25%{
          transform: scaleY(1);
        }
         50%{
          transform: scaleY(1);
        }
         75%{
          transform: scaleY(1);
        }
         100%{
          transform: scaleY(3);
        }

      }
      ul li:nth-child(1){
        animation-delay: .1s;
      }

      ul li:nth-child(2){
        animation-delay: .2s;
      }

      ul li:nth-child(3){
        animation-delay: .3s;
      }

      ul li:nth-child(4){
        animation-delay: .4s;
      }

      ul li:nth-child(5){
        animation-delay: .5s;
      }

      ul li:nth-child(6){
        animation-delay: .6s;
      }
```

**完整代码:**是以上两段代码的组合。

```html
<!DOCTYPE html>
<html>
<head>
<title>Dancing Bars</title>
  <style>
  ul{
      position: absolute;
      top:50%;
      left:50%;
      display: flex;
    }
    ul li{
      list-style: none;
      width: 6px;
      height: 20px;
      background: #262626;
      margin: 0 4px;
      animation: animate .7s infinite alternate 
      }
      @keyframes animate {
        0%{
          transform: scaleY(1);
        }
         25%{
          transform: scaleY(1);
        }
         50%{
          transform: scaleY(1);
        }
         75%{
          transform: scaleY(1);
        }
         100%{
          transform: scaleY(3);
        }

      }
      ul li:nth-child(1){
        animation-delay: .1s;
      }

      ul li:nth-child(2){
        animation-delay: .2s;
      }

      ul li:nth-child(3){
        animation-delay: .3s;
      }

      ul li:nth-child(4){
        animation-delay: .4s;
      }

      ul li:nth-child(5){
        animation-delay: .5s;
      }

      ul li:nth-child(6){
        animation-delay: .6s;
      }
  </style>
</head>
<body>
  <ul>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
  </ul>

</body>
</html>
```

**输出:**

![](img/e93e6af2104724124a032e4349d97cb7.png)