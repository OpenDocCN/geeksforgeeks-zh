# 如何在 CSS 中设置旋转元素的基础放置？

> 原文:[https://www . geeksforgeeks . org/如何设置旋转元素-基础-放置在 css 中/](https://www.geeksforgeeks.org/how-to-set-a-rotated-elements-base-placement-in-css/)

在本文中，我们将学习如何在 CSS 中设置旋转元素的基本位置。这可用于从某个点作为原点旋转元素。

**方法:**我们将使用 **[变换-原点](https://www.geeksforgeeks.org/css-transform-origin-property/)** 属性来设置旋转元素的基础位置。此属性可用于指定元素旋转的原点。它是元素旋转的点。它可以用于 2D 和三维旋转，但在本文中，我们将使用 2D 旋转。

**语法:**

```html
transform-origin: position
```

**例 1:** 在本例中，我们以长度单位指定位置。

## HTML

```html
<html>
<head>
  <style>
    .outer {
      margin: 50px;
      border: 1px double;

      /* This makes outer div relative so that 
      inner div on move according to user input */
      position: relative;
      height: 100px;
      width: 400px;
      background-color: lightgreen;
    }

    .box {
      position: absolute;
      border: 1px solid;
      background: url(
"https://contribute.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-logo.png")
        no-repeat;

      background-size: cover;
      height: 100px;
      width: 400px;

      /* Rotate image by 15 degrees */
      transform: rotate(15deg);

      /* Transforms image from initial position
      to 15px left and 40px from top */
      transform-origin: 15px 40px;
    }
  </style>
</head>
<body>
  <h1>CSS transform-origin Property</h1>
  <p>
    The CSS transform-origin Property is used to set
    the origin of the element's transformation
   </p>

  <div class="outer">
    <div class="box"></div>
  </div>
</body>
</html>
```