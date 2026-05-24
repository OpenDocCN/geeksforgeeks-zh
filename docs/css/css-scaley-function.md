# CSS | scaleY()函数

> 原文:[https://www.geeksforgeeks.org/css-scaley-function/](https://www.geeksforgeeks.org/css-scaley-function/)

**scaleY()函数**是一个内置函数，用于在 2D 平面中沿 y 轴调整元素的大小。它在垂直方向上缩放元素。

**语法:**

```html
scaleY( y )
```

**参数:**该功能接受单个参数 **y** ，该参数保存沿 y 轴的比例因子。

下面的例子说明了 CSS 中的 scaleY()函数:

**例 1:**

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title>CSS scaleY() function</title> 

    <style> 
        body {
            text-align:center;
        }
        h1 {
            color:green;
        }
        .scaleY_image {
            transform: scaleY(1.5);
        }
    </style> 
</head> 

<body> 
    <h1>GeeksforGeeks</h1>
    <h2>CSS scaleY() function</h2>
    <br><br>

    <img class="scaleY_image" src= 
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190710102234/download3.png"
        alt="GeeksforGeeks logo"> 
</body> 
</html>
```

**输出:**
![](img/9b9bb357d9553836ed910dae2719c816.png)

**例 2:**

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title>CSS scaleY() function</title> 

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
            transform: scaleY(2);
        }
    </style> 
</head> 

<body> 
    <h1>GeeksforGeeks</h1>
    <h2>CSS scaleY() function</h2>

    <div class="GFG">Welcome to GeeksforGeeks</div> 
</body> 
</html>
```

**输出:**
![](img/c69c335481eeac02160cca53bd666a2f.png)

**支持的浏览器:**scaleY()函数支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   旅行队
*   歌剧