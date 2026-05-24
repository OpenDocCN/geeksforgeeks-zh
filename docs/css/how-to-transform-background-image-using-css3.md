# 如何用 CSS3 变换背景图像？

> 原文:[https://www . geesforgeks . org/how-transform-background-image-using-css3/](https://www.geeksforgeeks.org/how-to-transform-background-image-using-css3/)

CSS 中的变换属性用于变换背景图像。在本文中，任务是变换背景图像。

**方法:**[**CSS 变换属性**](https://www.geeksforgeeks.org/css-transform-property/) 用于对元素应用二维或三维变换。transform 属性用于旋转、缩放和倾斜元素。

**语法:**

```html
.class_name { transform: value };
```

**注意:**将**溢出:隐藏**添加到具有变换属性的父组件中，以避免重叠效果。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <style>
    div.parent{
      margin-top: 15%;
      margin-left: 10%;
    }
    .child{
      /* transform image 50 degree */
      transform: rotate(50deg);
    }
  </style>
</head>

<body>
  <div class="parent">
    <div>
      <img src="gfg_complete_logo_2x-min.png" 
           class="child">
    </div>
  </div>
</body>

</html>
```

**输出:**

*   在变换背景图像之前:

    ![](img/0f354ee13bd29b12b1350f8e203aac34.png)

*   变换背景图像后:

    ![](img/f505bf743d2c1ab247d997c3bf225877.png)