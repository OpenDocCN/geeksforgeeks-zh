# 如何用 HTML 和 CSS 绘制半月形？

> 原文:[https://www . geeksforgeeks . org/如何使用 html 和 css 绘制半月图/](https://www.geeksforgeeks.org/how-to-draw-a-half-moon-using-html-and-css/)

可以使用 HTML 和 CSS 绘制各种形状，半月的形状也是如此，这个形状可以通过使用一些 CSS 属性操纵 T2 div 元素来绘制。

**HTML 代码:**在这个部分我们有一个基本的 **div** 标签。

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" 
        content="width=device-width,
                 initial-scale=1.0">
  <title>Half Moon</title>
</head>
<body>
  <div></div>   
</body>
</html>
```

**CSS 代码:**在本节中，我们通过操纵 **div** 元素来绘制半月，我们将使用**框影**和**边框半径**属性来绘制半月。

```html
<style>
  *{
     margin: 0;
     padding: 0;
     background-color: black;

   }
   /*Drawing the half moon by manipulating the div box*/
   div{
     position: absolute;
     top: 50%;
     left: 50%;
     transform: translate(-50%, -50%);
     height: 100px;
     width: 100px;
     box-shadow: -15px 15px 0 5px white  ;
     border-radius: 50%;
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
  <title>Half Moon</title>
</head>
<style>
  *{
     margin: 0;
     padding: 0;
     background-color: black;

   }
   /*Drawing the half moon by
     manipulating the div box*/
   div{
     position: absolute;
     top: 50%;
     left: 50%;
     transform: translate(-50%, -50%);
     height: 100px;
     width: 100px;
     box-shadow: -15px 15px 0 5px white  ;
     border-radius: 50%;
   }
  </style>
<body>

  <div></div>   
</body>
</html>
```

**输出:**

![](img/dce4181a0760d354ef1ca169c64fa871.png)