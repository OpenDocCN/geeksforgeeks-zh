# SVG 矩形元素。ry Property

> 原文:[https://www.geeksforgeeks.org/svg-rectelement-ry-property/](https://www.geeksforgeeks.org/svg-rectelement-ry-property/)

**SVG 矩形元素属性**用于返回对应于给定矩形角度元素属性的 SVGAnimatedLength 对象。

**语法:**

```html
RectElement.ry
```

**返回值:**该属性返回一个 SVGAnimatedLength 对象，该对象可用于获取矩形元素的“ry”值和其他属性。

**例 1:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body>
    <h1 style="color: green">
        GeeksforGeeks
    </h1>

    <h3>SVG RectElement.ry property</h3>

    <svg width="300" height="300" 
        xmlns="http://www.w3.org/2000/svg">

        <rect width="100" height='190' 
            fill="green" id="gfg" rx=10 ry=30 />

        <script>
            var g = document.getElementById("gfg");
            console.log(g.ry)
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/31a13ec57eeb6220933473ec361f5f22.png)

**例 2:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body>
    <h1 style="color: green">
        GeeksforGeeks
    </h1>

    <h3>SVG RectElement.ry property</h3>

    <svg width="300" height="300" 
        xmlns="http://www.w3.org/2000/svg">

        <rect width="100" height='190' 
            fill="green" id="gfg" rx=10% ry=35% />

        <script>
            var g = document.getElementById("gfg");
            console.log(g.ry)
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/a991697af0f4dc3a6f9b8c9e9b5b67ef.png)