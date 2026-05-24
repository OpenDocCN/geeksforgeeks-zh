# 如何使用 CSS 创建波浪加载器？

> 原文:[https://www . geesforgeks . org/how-create-wave-loader-use-CSS/](https://www.geeksforgeeks.org/how-to-create-wave-loader-using-css/)

一个波形加载器可以在网站中使用，当有东西加载时，它会提供更好的用户体验。波形加载器可以很容易地使用 HTML 和 CSS 创建。

**HTML 代码:**在本节中，我们将创建一个基本的 *div* 标签，该标签由内部的各种 *span 标签组成。*

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" 
        content="width=device-width, 
                 initial-scale=1.0">
  <title>Wave Loader</title>
</head>
<body>
  <div>
    <span></span>
    <span></span>
    <span></span>
    <span></span>
    <span></span>
    <span></span>
  </div>
</body>
</html>
```

**CSS 代码:**在本节中，我们将首先使用一些基本的 CSS 属性设计 *span* 元素，然后我们将使用*第 n 个子()选择器*选择每个 span 元素，即第 n 个子，然后我们将使用*@关键帧*规则创建加载动画。

```html
<style>
 *{
   margin: 0;
   padding: 0;
  }

  div{
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    display: flex;
    align-items: center;
  }
  span{
    height: 30px;
    width: 7px;
    margin-right: 10px;
    background-color: green;
    animation: loading 1s linear infinite;
  }
  span:nth-child(1){
    animation-delay: 0.1s;
  }
  span:nth-child(2){
    animation-delay: 0.2s;
  }
  span:nth-child(3){
    animation-delay: 0.3s;
  }
  span:nth-child(4){
    animation-delay: 0.4s;
  }
  span:nth-child(5){
    animation-delay: 0.5s;
  }
// @keyframes for animation
  @keyframes loading {
    0%{
      height: 0;
    }
    25%{
      height: 25px;
    }
    50%{
      height: 50px;
    }
    100%{
      height: 0;
    }

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
  <title>Wave Loader</title>
</head>
<style>
  *{
    margin: 0;
    padding: 0;
   }

   div{
     position: absolute;
     top: 50%;
     left: 50%;
     transform: translate(-50%, -50%);
     display: flex;
     align-items: center;
   }
   span{
     height: 30px;
     width: 7px;
     margin-right: 10px;
     background-color: green;
     animation: loading 1s linear infinite;
   }
   span:nth-child(1){
     animation-delay: 0.1s;
   }
   span:nth-child(2){
     animation-delay: 0.2s;
   }
   span:nth-child(3){
     animation-delay: 0.3s;
   }
   span:nth-child(4){
     animation-delay: 0.4s;
   }
   span:nth-child(5){
     animation-delay: 0.5s;
   }

   @keyframes loading {
     0%{
       height: 0;
     }
     25%{
       height: 25px;
     }
     50%{
       height: 50px;
     }
     100%{
       height: 0;
     }

   }

 </style>
<body>
  <div>
    <span></span>
    <span></span>
    <span></span>
    <span></span>
    <span></span>
    <span></span>
  </div>
</body>
</html>
```

**输出:**

![](img/76ef76c5c2437ebaaabeb4bdc229af2f.png)