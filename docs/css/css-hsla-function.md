# CSS | hsla()功能

> 原文:[https://www.geeksforgeeks.org/css-hsla-function/](https://www.geeksforgeeks.org/css-hsla-function/)

hsla()函数是 CSS 中的一个内置函数，用于使用色调饱和度亮度 Alpha (HSLA)模型定义颜色。

**语法:**

```html
hsla( hue, saturation, lightness, alpha )
```

**参数:**该功能接受四个参数，如上所述，描述如下:

*   **色相:**此参数用于定义色轮上的度数。它的值介于 0 到 360 之间，其中 0 或 360 代表红色，120 代表绿色，240 代表蓝色。
*   **饱和度:**此参数用于定义饱和度，其中 0%代表灰色阴影，100%代表全色。
*   **明度:**此参数用于定义明度，其中 0%代表黑色，50%代表正常，100%代表白色。
*   **alpha:** 此参数用于定义不透明度，该值介于 0.0(完全透明)和 1.0(完全不透明)之间。

下面的程序说明了 CSS 中的 hsla()函数:

**程序:**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>hsla function</title>
        <style> 
            .gfg1 {
                background-color:hsla(120, 100%, 40%, 0.3);
                text-align:center;
            }
            .gfg2 {
                background-color:hsla(120, 100%, 75%, 0.3);
                text-align:center
            }
            .gfg3 {
                background-color:hsla(120, 100%, 20%, 0.3);
                text-align:center
            }
            .gfg {
                font-size:40px;
                font-weight:bold;
                color:green;
                text-align:center;
            }
            h1 {
                text-align:center;
            }
        </style>
    </head>
    <body>
        <div class = "gfg">GeeksforGeeks</div>
        <h1>The hsla() Function</h1>
        <p class = "gfg1">Green</p>
        <p class = "gfg2">Light green</p>
        <p class = "gfg3">Dark green</p>
    </body>
</html>
```

**输出:**
![](img/79240ab0164871d8539a5062d04053bd.png)

**支持的浏览器:**HSLA()功能支持的浏览器如下:

*   Chrome 1.0 及以上版本
*   Internet Explorer 9.0 及以上版本
*   Firefox 3.0 及以上版本
*   Safari 3.1 及以上版本
*   Opera 10.0 及以上版本