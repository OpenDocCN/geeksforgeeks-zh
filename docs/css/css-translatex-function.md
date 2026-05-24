# CSS | translateX()函数

> 原文:[https://www.geeksforgeeks.org/css-translatex-function/](https://www.geeksforgeeks.org/css-translatex-function/)

**translateX()函数**是一个内置函数，用于沿水平轴重新定位元素。

**语法:**

```html
translateX( t )
```

**参数:**该功能接受单参数 **t** ，该参数保存 x 轴对应的平移长度。

下面的例子说明了 CSS 中的 translateX()函数:

**例 1:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>
      CSS translateX() function
  </title>
    <style>
        body {
            text-align: center;
        }

        h1 {
            color: green;
        }

        .translateX_image {
            transform: translateX(100px);
        }
    </style>
</head>

<body>
    <h1>GeeksforGeeks</h1>
    <h2>CSS translateX() function</h2>

    <h4>Original Image</h4>
    <img src=
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190710102234/download3.png"
         alt="GeeksforGeeks logo">
    <br>

    <h4>Translated image</h4>
    <img class="translateX_image" 
         src=
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190710102234/download3.png"
         alt="GeeksforGeeks logo">
</body>

</html>
```

**输出:**
![](img/153077be31e4ba9c51ac1f1a168e1d6e.png)

**例 2:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>
      CSS translateX() function
  </title>
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
        }

        .geeks {
            transform: translateX(100px);
        }
    </style>
</head>

<body>
    <h1>GeeksforGeeks</h1>
    <h2>
      CSS translateX() function
  </h2>

    <h4>Original Element</h4>
    <div class="GFG">
      Welcome to GeeksforGeeks
  </div>

    <h4>Translated Element</h4>
    <div class="GFG geeks">
      Welcome to GeeksforGeeks
  </div>
</body>

</html>
```

**输出:**
![](img/e08da52854da56e40bc20a4afacccbaf.png)

**支持的浏览器:****translateX()功能**支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   旅行队
*   歌剧