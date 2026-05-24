# SVG `<foreignObject>`元素

> 原文:[https://www.geeksforgeeks.org/svg-foreignobject-element/](https://www.geeksforgeeks.org/svg-foreignobject-element/)

SVG 代表可缩放矢量图形。它可以用来制作像在 HTML 画布中的图形和动画。

SVG 的 **< foreignObject >** 元素包含来自不同 XML 命名空间的元素。这是一个可扩展性点，允许用户代理提供超出本规范中定义的图形呈现功能。

**语法:**

```html
<foreignObject x = "The x coordinate of the foreignObject"
         y = "The x coordinate of the foreignObject"
         width = "The width of the foreignObject" 
         height = "The height of the foreignObject">
</foreignObject>

```

**属性:**

*   x = foreignObject 的 x 坐标。
*   y =对象的 x 坐标。
*   宽度=对象的宽度。
*   高度=对象的高度。

**示例:**

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content=
        "width=device-width,
         initial-scale=1.0">
</head>

<body>
    <svg viewBox="500 500 ">
        <style>
            div {
                color: green;
                font: 18px serif;
                height: 100%;
                overflow: auto;
                background-color: black;
            }
        </style>
        <foreignObject x="100" y="25" 
            width="160" height="160">
            <div>
                <br><br>GEEKSFORGEEKS<br><br>
            </div>
        </foreignObject>
    </svg>
</body>

</html>
```

**输出:**

![](img/2c6aff418a24b91798acbbc7c95f7ad8.png)

**支持的浏览器:**

*   铬
*   边缘
*   歌剧
*   微软公司出品的 web 浏览器
*   旅行队
*   火狐浏览器