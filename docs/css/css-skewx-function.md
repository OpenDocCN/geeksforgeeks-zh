# CSS | skyx()函数

> 原文:[https://www.geeksforgeeks.org/css-skewx-function/](https://www.geeksforgeeks.org/css-skewx-function/)

**skew()函数**是一个内置函数，用于在 2D 平面中沿水平方向变换元素。

**语法:**

```html
skewX( a )
```

**参数:**该功能接受单个参数 **a** ，该参数保存代表水平轴的角度。

下面的例子说明了 CSS 中的 skewX()函数:

**例 1:**

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title>CSS skewX() function</title> 

    <style> 
        body {
            text-align:center;
        }
        h1 {
            color:green;
        }
        .skewX_image {
            transform: skewX(30deg);
        }
    </style> 
</head> 

<body> 
    <h1>GeeksforGeeks</h1>
    <h2>CSS skewX() function</h2>

    <img class="skewX_image" src= 
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190710102234/download3.png"
        alt="GeeksforGeeks logo"> 
</body> 

</html>                    
```

**输出:**
![](img/5b28d084580e5b0083a5f2dc278e3a7e.png)

**例 2:**

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title>CSS skewX() function</title> 

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
            transform: skewX(45deg);
        }
    </style> 
</head> 

<body> 
    <h1>GeeksforGeeks</h1>
    <h2>CSS skewX() function</h2>

    <div class="GFG">Welcome to GeeksforGeeks</div> 
</body> 

</html>                    
```

**输出:**
![](img/ff4e8be9fc29f714a3e1baa9a99fa255.png)

**支持的浏览器:**skyx()函数支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   旅行队
*   歌剧