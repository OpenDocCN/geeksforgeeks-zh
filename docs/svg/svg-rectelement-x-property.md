# SVG 矩形元素. x 属性

> 原文:[https://www.geeksforgeeks.org/svg-rectelement-x-property/](https://www.geeksforgeeks.org/svg-rectelement-x-property/)

属性 返回一个对应于给定矩形角度元素属性的 SVGAnimatedLength

**语法:**

```html
RectElement.x
```

**返回值:**该属性返回 SVGAnimatedLength 对象，该对象可用于获取矩形元素的 x 轴

**例 1:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body>
    <svg width="350" height="150" 
        xmlns="http://www.w3.org/2000/svg">

        <rect width="100" height='100' 
            fill="green" id="gfg" x=20 y=20 />

        <script>
            var g = document.getElementById("gfg");
            console.log(g.x);
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/9aba2b6157904a48b9010a235965cfc5.png)

**例 2:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body>
    <svg width="350" height="150" 
        xmlns="http://www.w3.org/2000/svg">

        <rect width="100" height='100' 
            fill="green" id="gfg" x=30 y=20 />

        <script>
            var g = document.getElementById("gfg");
            console.log(g.x)
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/2c0bd15e68ac54a4ffc61ee34db0a9c7.png)