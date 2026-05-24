# CSS | rotateX()函数

> 原文:[https://www.geeksforgeeks.org/css-rotatex-function/](https://www.geeksforgeeks.org/css-rotatex-function/)

**rotateX()函数**是一个内置函数，用于围绕 x 轴旋转元素。

**语法:**

```html
rotateX( angle )
```

**参数:**该功能接受单参数**角度**，代表旋转角度。正负角度分别顺时针和逆时针旋转元素。

以下示例说明了 CSS 中的 rotateX()函数:
**示例 1:**

```html
<!DOCTYPE html> 
<html> 
<head> 
    <title>CSS rotateX() function</title> 
    <style> 
        body {
            text-align:center;
        }
        h1 {
            color:green;
        }
        .rotateX_image {
            transform: rotateX(60deg);
        }
    </style> 
</head> 

<body> 
    <h1>GeeksforGeeks</h1>
    <h2>CSS rotateX() function</h2>

    <img class="rotateX_image" src= 
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190710102234/download3.png"
        alt="GeeksforGeeks logo"> 
</body> 
</html>
```

**输出:**
![](img/ceef25643f1d3615076536d2c5510928.png)

**例 2:**

```html
<!DOCTYPE html> 
<html> 
<head> 
    <title>CSS rotateX() function</title> 
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
            transform: rotateX(60deg);
        }
    </style> 
</head> 

<body> 
    <h1>GeeksforGeeks</h1>
    <h2>CSS rotateX() function</h2>

    <div class="GFG">Welcome to GeeksforGeeks</div> 
</body> 
</html>
```

**输出:**
![](img/5e11c44317684366ac37c876acc459fb.png)

**支持的浏览器:****rotateX()功能**支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   旅行队
*   歌剧