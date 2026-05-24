# CSS |径向渐变()函数

> 原文:[https://www.geeksforgeeks.org/css-radial-gradient-function/](https://www.geeksforgeeks.org/css-radial-gradient-function/)

径向渐变()函数是 CSS 中的一个内置函数，用于设置一个径向渐变作为背景图像。它从一个点开始，向外发散。默认情况下，第一种颜色从元素的中心位置开始，然后向元素的边缘渐变到结束颜色。渐变以相同的速率发生，直到指定。
**语法:**

```html
background-image: radial-gradient( shape size at position, start-color, ..., last-color );
```

**参数:**该功能接受很多参数，如下所示:

*   **形状:**此参数用于定义渐变的形状。它有两个可能的值圆或椭圆。默认形状值为椭圆形。
*   **大小:**此参数用于定义渐变的大小。可能的值有:最远角(默认)、最近边、最近角、最远边。
*   **位置:**此参数用于定义坡度的位置。默认值为中心。
*   **起始颜色、…、最后颜色:**此参数用于保存颜色值，后跟可选的停止位置。

下面的例子说明了 CSS 中的径向渐变()函数:
**程序 1:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
    <head>
        <title>CSS Gradients</title>
        <style>
            #main {
                height: 250px;
                width: 600px;
                background-color: white;
                background-image: radial-gradient(#090, #fff, #2a4f32);
            }
            .gfg {
                text-align:center;
                font-size:40px;
                font-weight:bold;
                padding-top:80px;
            }
            .geeks {
                font-size:17px;
                text-align:center;
            }
        </style>
    </head>
    <body>
        <div id="main">
            <div class = "gfg">GeeksforGeeks</div>
            <div class = "geeks">A computer science portal for geeks</div>
        </div>
    </body>
</html>                   
```

**输出:**

![](img/36cc6fd1f4f01af9d05a0c5484c9a0da.png)

**节目 2:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
    <head>
        <title>CSS Gradients</title>
        <style>
            #main {
                height: 400px;
                width: 600px;
                background-color: white;
                background-image: radial-gradient(circle, green, white, blue);
            }
            .gfg {
                text-align:center;
                font-size:40px;
                font-weight:bold;
                padding-top:155px;
            }
            .geeks {
                font-size:17px;
                text-align:center;
            }
        </style>
    </head>
    <body>
        <div id="main">
            <div class = "gfg">GeeksforGeeks</div>
            <div class = "geeks">A computer science portal for geeks</div>
        </div>
    </body>
</html>                   
```

**输出:**

![](img/413a1f3f0a6fbd36a421ab4aea38f498.png)

**支持的浏览器:**

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队