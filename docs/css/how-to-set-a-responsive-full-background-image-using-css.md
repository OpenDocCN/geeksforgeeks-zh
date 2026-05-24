# 如何使用 CSS 设置响应性的全背景图像？

> 原文:[https://www . geesforgeks . org/how-set-a-responsive-full-background-image-use-CSS/](https://www.geeksforgeeks.org/how-to-set-a-responsive-full-background-image-using-css/)

本文的目的是使用 CSS 设置一个响应的全背景图像。

要使用 CSS 设置响应性全背景图像，我们将使用 CSS [**背景大小属性**](https://www.geeksforgeeks.org/css-background-size-property/) ，该属性具有值 *auto* ，该值告诉浏览器基于容器自动缩放图像的*宽度*和*高度*，以使元素居中。对于小尺寸设备，我们将添加媒体查询，以减小图像文件的大小，从而快速加载。

**语法:**

```html
background-size: auto; 
```

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" 
          content="IE=edge" />
    <meta name="viewport" 
          content="width=device-width, initial-scale=1.0" />
    <style>
      body {
        /* Add image */
        background-image: url(
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20210324142236/gfg_complete_logo_2x-min1.png");

        /* Make image center */
        background-position: center center;

        /* Make image fixed */
        background-attachment: fixed;

        /* Not repeat images */
        background-repeat: no-repeat;

        /* Set background size auto */
        background-size: auto;
      }

      /* Media query for mobile devices  */
      @media only screen and (max-width: 767px) {
        body {
          background-image: url(
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20210324142236/gfg_complete_logo_2x-min1.png");
        }
      }
    </style>
  </head>
  <body>
  </body>
</html>
```

**输出:**

![](img/f5297cd821b70c0f6d538e2187d8dc9b.png)