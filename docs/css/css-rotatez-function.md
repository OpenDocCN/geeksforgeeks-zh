# CSS | rotateZ()函数

> 原文:[https://www.geeksforgeeks.org/css-rotatez-function/](https://www.geeksforgeeks.org/css-rotatez-function/)

**rotateZ()函数**是一个内置函数，用于围绕 z 轴旋转元素。

**语法:**

```html
rotateZ( angle )
```

**参数:**该功能接受单参数**角度**，代表旋转角度。正负角度分别顺时针和逆时针旋转元素。

下面的例子说明了 CSS 中的 rotateZ()函数:

**例 1:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS rotateZ() function</title>

    <style>
        body {
            text-align: center;
        }
        h1 {
            color: green;
        }
        .rotateZ_image {
            transform: rotateZ(45deg);
        }
    </style>
</head>

<body>
    <h1>GeeksforGeeks</h1>
    <h2>CSS rotateZ() function</h2>

    <br><br>

    <img class="rotateZ_image" src=
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190710102234/download3.png"
         alt="GeeksforGeeks logo">
</body>

</html>                                    
```

**输出:**
![](img/9dfa70a2c73cd9b3cab496c8e196f8ad.png)

**例 2:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS rotateZ() function</title>

    <style>
        body {
            text-align: center;
        }
        h1 {
            color: green;
        }
        .GFG {
            font-size: 35px;
            font-weight: bold;
            color: green;
            transform: rotateZ(45deg);
        }
    </style>
</head>

<body>
    <h1>GeeksforGeeks</h1>
    <h2>CSS rotateZ() function</h2>

    <br><br>

    <div class="GFG">Welcome to GeeksforGeeks</div>
</body>

</html>
```

**输出:**
![](img/f8678c0f0c58b9f3794f6fb4b4949a6a.png)

**支持的浏览器:****rotateZ()功能**支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队