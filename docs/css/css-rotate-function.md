# CSS |旋转()功能

> 原文:[https://www.geeksforgeeks.org/css-rotate-function/](https://www.geeksforgeeks.org/css-rotate-function/)

**rotate()** 函数是一个内置函数，用于根据给定的角度作为参数旋转元素。角度可以根据度数、梯度、弧度或转角进行设置。

**语法:**

```html
rotate( angle )
```

**参数:**该功能接受单参数**角度**，代表旋转角度。正负角度分别顺时针和逆时针旋转元素。

以下示例说明了 CSS 中的 rotate()函数:
**示例 1:**

```html
<!DOCTYPE html> 
<html> 
<head> 
    <title>CSS rotate() function</title> 
    <style> 
        body {
            text-align:center;
        }
        h1 {
            color:green;
        }
        .rotate_image {
            transform: rotate(45deg);
        }
    </style> 
</head> 

<body> 
    <h1>GeeksforGeeks</h1>
    <h2>CSS rotate() function</h2>
    <br><br>

    <img class="rotate_image" src= 
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190710102234/download3.png"
        alt="GeeksforGeeks logo"> 
</body> 
</html>
```

**输出:**
![](img/b097fa62d26e929c0b5d9d41de0790a1.png)

**例 2:**

```html
<!DOCTYPE html> 
<html> 
<head> 
    <title>CSS rotate() function</title> 
    <style> 
        body {
            text-align:center;
        }
        h1 {
            color:green;
        }
        .GFG {
            font-size:35px;
            font-weight:bold;
            color:green;
            transform: rotate(30deg);
        }
    </style> 
</head> 

<body> 
    <h1>GeeksforGeeks</h1>
    <h2>CSS rotate() function</h2>
    <br><br>

    <div class="GFG">Welcome to GeeksforGeeks</div> 
</body> 
</html>                     
```

**输出:**
![](img/c9e31288573c30a173ad5070207c3025.png)

**支持的浏览器:****旋转()功能**支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   旅行队
*   歌剧