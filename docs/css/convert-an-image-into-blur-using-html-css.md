# 使用 HTML/CSS 将图像转换为模糊

> 原文:[https://www . geesforgeks . org/convert-a-image-in-blur-using-html-CSS/](https://www.geeksforgeeks.org/convert-an-image-into-blur-using-html-css/)

给定一个图像，任务是使用 CSS 属性将图像转换为模糊图像。在 CSS 中，滤镜属性用于将图像转换为模糊图像。Filter 属性主要用于设置图像的视觉效果。

**语法:**

```html
filter: blur()

```

**示例 1:** 本示例使用模糊滤镜将图像转换为模糊图像。

**原图:**
![](img/3078dac92dca2c58e7e25dd9979b36a6.png)

```html
<!DOCTYPE html> 
<html> 
    <head> 
        <title>Convert into blur image</title> 
        <style> 
            img { 
                -webkit-filter: blur(4px); 
                filter: blur(4px); 
            } 
            h1 { 
                color:green; 
            } 
        </style> 
    </head> 
    <body> 
        <center> 
        <h1>GeeksforGeeks</h1> 
        <h2>Blur Image</h2> 
        <img src= 
"https://media.geeksforgeeks.org/wp-content/uploads/interview-preparation-2.png"
        width="500px" height="250px" alt="filter applied" /> 
        </center> 
    </body> 
</html> 
```

**输出:**
![](img/4bbbfb3c93ec45650912bc06a2b5e320.png)

**示例 2:** 本示例使用模糊滤镜创建背景模糊图像。
**原图:**
![](img/506d5b06554d6ff2062e8b2e9814593f.png)

```html
<!DOCTYPE html> 
<html> 
    <head> 
        <title>
            Convert into blur image
        </title> 

        <style> 
            img { 
                -webkit-filter: blur(4px); 
                filter: blur(4px); 
            } 
            h1 { 
                color:green; 
            } 
            .backgr-text {
                position: absolute;
                top: 20%;
                left: 50%;
                transform: translate(-50%, -50%);
                text-align: center;
            }
        </style> 
    </head> 

    <body> 
        <center> 
            <img src= 
"https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-logo.png"
            width="500px" height="250px" alt="filter applied" /> 

            <div class="backgr-text">
                <h1>GeeksforGeeks</h1>
                <h2>Blurred Background Image</h2>
            </div>
        </center> 
    </body> 
</html>                    
```

**输出:**
![](img/d8a80f9ffd5bf4dcd1dfb9ee458dbf84.png)