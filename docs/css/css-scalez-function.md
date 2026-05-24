# CSS | scaleZ()函数

> 原文:[https://www.geeksforgeeks.org/css-scalez-function/](https://www.geeksforgeeks.org/css-scalez-function/)

**scaleZ()函数**是一个内置函数，用于沿 z 轴调整元素的大小。

**语法:**

```html
scaleZ( z )
```

**参数:**该功能接受单个参数 **z** ，该参数保存 z 轴的比例因子。

以下示例说明了 CSS 中的 scaleZ()函数:

**例 1:**

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title>CSS scaleZ() function</title> 

    <style> 
        body {
            text-align:center;
        }
        h1 {
            color:green;
        }
        .scaleZ_image {
            transform: perspective(500px) scaleZ(3) rotateX(45deg);
        }
    </style> 
</head> 

<body> 
    <h1>GeeksforGeeks</h1>
    <h2>CSS scaleZ() function</h2>

    <img class="scaleZ_image" src= 
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190710102234/download3.png"
        alt="GeeksforGeeks logo"> 
</body> 

</html>
```

**输出:**
![](img/97866e5f1994d5dc99ff2087763c4429.png)

**例 2:**

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title>CSS scaleZ() function</title> 

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
            transform: perspective(300px) scaleZ(3) rotateX(45deg);
        }
    </style> 
</head> 

<body> 
    <h1>GeeksforGeeks</h1>
    <h2>CSS scaleZ() function</h2>

    <div class="GFG">Welcome to GeeksforGeeks</div> 
</body> 
</html>
```

**输出:**
![](img/73b13ee4551fe1bd0fa4e62c52d16ad2.png)

**支持的浏览器:**scaleZ()函数支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   旅行队
*   歌剧