# 用 CSS 设置背景图像的大小？

> 原文:[https://www . geeksforgeeks . org/set-the-size-of-background-image-use-CSS/](https://www.geeksforgeeks.org/set-the-size-of-background-image-using-css/)

**背景尺寸属性**用于使用 CSS 设置背景图像尺寸。使用高度和宽度属性设置背景图像的大小。

**语法:**

```html
background-size: width height;
```

**注:**

*   如果省略第一个值，则图像将采用其原始宽度。
*   如果省略第二个值，则图像将采用其原始高度。

**示例 1:** 本示例将背景尺寸设置为宽度和高度。

```html
<!DOCTYPE html> 
<html> 
    <head> 
        <title> 
            Set the size of background image
        </title> 

        <style>
            #myDiv {
                height: 200px;
                width: 400px;
                background: 
url("https://media.geeksforgeeks.org/wp-content/uploads/gfgbg.png");
                background-size: 400px 200px;

            }
        </style>
    </head>

    <body> 
        <div id= "myDiv"></div>
    </body> 
</html>                    
```

**输出:**
![](img/69fd10688aa1e45ba9d51d142119bd2f.png)

**示例 2:** 本示例将背景大小设置为百分比。

```html
<!DOCTYPE html> 
<html> 
    <head> 
        <title> 
            Set the size of background image
        </title> 

        <style>
            #myDiv {
                height: 200px;
                width: 400px;
                background: 
url("https://media.geeksforgeeks.org/wp-content/uploads/gfgbg.png");

                /* Set the background-size in percentage */
                background-size: 70%;
                background-repeat: no-repeat; 
            }
        </style>
    </head>

    <body> 
        <div id= "myDiv"></div>
    </body> 
</html>                     
```

**输出:**
![](img/3463c4fe3aeb2af94cb6f3f87b00581d.png)