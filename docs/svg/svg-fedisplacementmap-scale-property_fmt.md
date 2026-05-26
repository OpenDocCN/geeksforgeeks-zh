# SVG FEDisplacementMap.scale 属性

> 原文: [https://www.geeksforgeeks.org/svg-fedisplacementmap-scale-property/](https://www.geeksforgeeks.org/svg-fedisplacementmap-scale-property/)

SVG `<feDisplacementMap>` 的 `scale` 属性返回一个对应于该元素比例分量的 `SVGAnimatedNumber` 对象。

## 语法

```html
var a = FEDisplacementMap.scale
```

## 返回值

该属性返回一个对应于元素比例分量的 `SVGAnimatedNumber` 对象。

## 例 1

```html
<!DOCTYPE html>
<html>

<body>
    <svg width="200" height="200"
        viewBox="0 0 220 220">

        <filter id="displacementFilter">
            <feTurbulence type="turbulence"
                baseFrequency="1" numOctaves="2"
                result="turbulence"/>
            <feDisplacementMap in2="turbulence"
                in="SourceGraphic" scale="50"
                xChannelSelector="R"
                yChannelSelector="B" id="gfg"/>
        </filter>

        <circle cx="100" cy="100" r="100"
            stroke="green" style="filter: url(#displacementFilter)" />

        <script type="text/javascript">
            var g = document.getElementById("gfg");
            console.log(g.scale)
            console.log("scale value is : ", g.scale.baseVal)
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/52087b9e31f86d04d27c2a5ab72b102b.png)

## 例 2

```html
<!DOCTYPE html>
<html>

<body>
    <svg width="200" height="200"
        viewBox="0 0 220 220">

        <filter id="displacementFilter">
            <feTurbulence type="turbulence"
                baseFrequency="5" numOctaves="2"
                result="turbulence" />
            <feDisplacementMap in2="abc"
                in="SourceGraphic" scale="200"
                xChannelSelector="B"
                yChannelSelector="R" id="gfg" />
        </filter>

        <rect width="250" height="250" style="filter: url(#displacementFilter)" />

        <script type="text/javascript">
            var g = document.getElementById("gfg");
            console.log(g.scale)
            console.log("scale value is : ", g.scale.baseVal)
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/352a93059512dd3fdd61728ed4f96fe1.png)

## 支持的浏览器

*   Google Chrome
*   Edge
*   Firefox
*   Safari
*   Opera
*   Internet Explorer