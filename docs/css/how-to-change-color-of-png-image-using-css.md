# 如何使用 CSS 改变 PNG 图像的颜色？

> 原文:[https://www . geesforgeks . org/如何更改 png 图像的颜色-使用-css/](https://www.geeksforgeeks.org/how-to-change-color-of-png-image-using-css/)

给定一个图像，任务是使用 CSS 改变图像颜色。使用滤镜功能改变 png 图像颜色。Filter 属性主要用于设置图像的视觉效果。过滤函数有许多属性值。

```html
filter: none|blur()|brightness()|contrast()|drop-shadow()|grayscale()
        |hue-rotate()|invert()|opacity()|saturate()|sepia()|url();
```

**示例 1:** 本示例使用灰度滤镜将彩色图像更改为灰度图像。

```html
<!-- HTML code to change the png image color 
        using filter property -->
<!DOCTYPE html> 
<html> 
    <head> 
        <title>Convert into grayscale image</title> 
        <style> 
            img { 
                filter: grayscale(10); 
            } 
        </style> 
    </head> 

    <body> 
        <h2>Grayscale Image</h2> 
        <img src= 
"https://media.geeksforgeeks.org/wp-content/uploads/interview-preparation-2.png"
        width="500px" height="250px" alt="filter applied" /> 
    </body> 
</html> 
```

**输出:**
**原图:**
![](img/93a5bd47fc64d546315c31af548efa09.png)
**应用滤镜后:**
![](img/390d47683ca8cb94574306f0e87e44e8.png)

**示例 2:** 本示例对图像使用了许多滤镜。

```html
<!-- HTML code to change the png image color 
        using filter property -->
<!DOCTYPE html> 
<html> 
    <head> 
        <title>Convert image into different color</title> 
        <style> 
            img { 
                width:40%;
                float:left;
            }
            .image1 {
                filter: invert(100%);
            }
            .image2 {
                filter: sepia(100%);   
            }
        </style> 
    </head> 

    <body> 
        <img class = "image1" src= 
"https://media.geeksforgeeks.org/wp-content/uploads/interview-preparation-2.png"
        width="500px" height="250px" alt="filter applied" /> 

        <img class = "image2" src= 
"https://media.geeksforgeeks.org/wp-content/uploads/interview-preparation-2.png"
        width="500px" height="250px" alt="filter applied" /> 
    </body> 
</html> 
```

**输出:**
![](img/2a3029e15edcf29ed513df3b42323641.png)