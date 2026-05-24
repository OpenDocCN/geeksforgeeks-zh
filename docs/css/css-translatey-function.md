# CSS | translateY()功能

> 原文:[https://www.geeksforgeeks.org/css-translatey-function/](https://www.geeksforgeeks.org/css-translatey-function/)

**平移()函数**是一个内置函数，用于沿垂直轴重新定位元素。

**语法:**

```html
translateY( t )
```

**参数:**该功能接受单个参数 **t** ，该参数保存对应于 y 轴的平移长度。

下面的例子说明了 CSS 中的 **translateY()函数**:

**例 1:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>
      CSS translateY() function
  </title>
    <style>
        body {
            text-align: center;
        }

        h1 {
            color: green;
        }

        .translateY_image {
            transform: translateY(100px);
        }
    </style>
</head>

<body>
    <h1>GeeksforGeeks</h1>
    <h2>CSS translateY() function</h2>

    <h4>Original Image</h4>
    <img src=
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190710102234/download3.png" 
         alt="GeeksforGeeks logo">
    <br>

    <h4>Translated image</h4>
    <img class="translateY_image"
         src=
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190710102234/download3.png"
         alt="GeeksforGeeks logo">
</body>

</html>
```

**输出:**
![](img/9c7fd43cdc913768cb66e40ea56f4391.png)

**例 2:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>
      CSS translateY() function
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
            transform: translateY(100px);
        }
    </style>
</head>

<body>
    <h1>GeeksforGeeks</h1>
    <h2>CSS translateY() function</h2>

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
![](img/510b6ab9552f55462f534796cd78bdce.png)

**支持的浏览器:****translateY()功能**支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   旅行队
*   歌剧