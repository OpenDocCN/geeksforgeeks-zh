# 如何使用 HTML 和 CSS 绘制五边形？

> 原文:[https://www . geeksforgeeks . org/如何使用 html 和 css 绘制五边形/](https://www.geeksforgeeks.org/how-to-draw-a-pentagon-using-html-and-css/)

五边形是一个 5 边的多边形或几何形状，有 5 个内角，每个内角为 108 度。五边形可以使用简单的 HTML 和 CSS 绘制，下面几节将指导您如何绘制所需的形状。

**HTML 代码:**在本节中，我们将使用类名为**“五边形”的 *div* 类创建一个简单的 *div* 元素。**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" 
        content="width=device-width,
                 initial-scale=1.0">
  <title>Pentagon</title>
</head>
<body>
  <div class="pentagon"></div>   
</body>
</html>
```

**CSS 代码:**在本节中，我们将首先用一些基本的 CSS 属性设计 *div* 元素，并绘制*五边形，*我们将使用 CSS **:在**选择器之后，在元素内容之后插入一些内容，即在我们的例子中的 *div* 元素。

```html
<style>
*{
    margin: 0;
    padding: 0;
    background-color: white;

  }
  /* creating tthe pentagon shape */
  .pentagon{
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    height: 0;
    width: 180px;
    border-top: 180px solid rgb(0, 66, 128);
    border-left: 90px solid transparent;
    border-right: 90px solid transparent; 
  }

  .pentagon:after{
    position: absolute;
    content: '';
    border-bottom: 180px solid rgb(0, 66, 128);
    border-left: 180px solid transparent;
    border-right: 180px solid transparent;
    bottom: 180px;
    left: -90px;
  }
 </style>
```

**最终代码:**是以上两个代码段的组合。

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport"
        content="width=device-width,
                 initial-scale=1.0">
  <title>Pentagon</title>
</head>
<style>
  *{
      margin: 0;
      padding: 0;
      background-color: white;

    }
    /* creating tthe pentagon shape */
    .pentagon{
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      height: 0;
      width: 180px;
      border-top: 180px solid rgb(0, 66, 128);
      border-left: 90px solid transparent;
      border-right: 90px solid transparent; 
    }

    .pentagon:after{
      position: absolute;
      content: '';
      border-bottom: 180px solid rgb(0, 66, 128);
      border-left: 180px solid transparent;
      border-right: 180px solid transparent;
      bottom: 180px;
      left: -90px;
    }
   </style>
<body>
  <div class="pentagon"></div>   
</body>
</html>
```

**输出:**

![](img/d1ab7993a4a52fd187314f52ca0fc15f.png)