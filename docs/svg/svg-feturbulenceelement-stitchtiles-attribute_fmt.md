# SVG `feTurbulence` 元素的 `stitchTiles` 属性

> 原文：[https://www.geeksforgeeks.org/svg-feturbulenceelement-stitchtiles-attribute/](https://www.geeksforgeeks.org/svg-feturbulenceelement-stitchtiles-attribute/)

`SVG feTurbulence` 元素的 `stitchTiles` 属性返回与 `feTurbulence` 元素的 `stitchTiles` 组件对应的 `SVGAnimatedEnumeration` 对象。

**语法：**

```html
var a = FETurbulenceElement.stitchTiles
```

**返回值：** 该属性返回与 `feTurbulence` 元素的 `stitchTiles` 组件对应的 `SVGAnimatedEnumeration` 对象。

## 示例 1

```html
<!DOCTYPE html> 
<html>

<body>

<svg width="200" height="200"
        viewBox="0 0 220 220">

<filter id="FillPaint">

<feTurbulence id='gfg' type="turbulence"
                baseFrequency="0.5" numOctaves="2"
                seed="5" stitchTiles="stitch" />

<feDisplacementMap in2="turbulence"
                in="SourceGraphic" scale="50"
                xChannelSelector="B"
                yChannelSelector="B" />

</filter>

<rect width="200" height="200"
            style=" fill:green; 
            filter: url(#FillPaint);" />

<script type="text/javascript">
            var g = document.getElementById("gfg");
            console.log(g.stitchTiles);
            console.log("stitchTiles value is :",
                g.stitchTiles.baseVal);
        </script> 
    </svg> 
</body>

</html>
```

**输出：**

![](img/19cedbeb7d74380aebd8dd5eaf78df20.png)

## 示例 2

```html
<!DOCTYPE html> 
<html>

<body>

<svg width="400" height="400"
        viewBox="0 0 250 250">

<filter id="FillPaint">

<feTurbulence id="gfg" type="fractalNoise"
                baseFrequency="2" numOctaves="2"
                seed="1" stitchTiles="stitch"
                result="turbulence" />

<feDisplacementMap in2="turbulence"
                in="SourceGraphic" scale="50"
                xChannelSelector="B"
                yChannelSelector="B" />

</filter>

<ellipse cx="100" cy="60" rx="100"
            ry="50" style=" fill: green; 
            filter: url(#FillPaint);" /> 
        <script type="text/javascript">
            var g = document.getElementById("gfg");
            console.log(g.stitchTiles);
            console.log("stitchTiles value is :",
                g.stitchTiles.baseVal);
        </script>
    </svg> 
</body>

</html>
```

**输出：**

![](img/8500e3cdc374fefa4e8674c7555147fd.png)

**支持的浏览器：**

*   Google Chrome
*   Edge
*   Firefox
*   Safari
*   Opera
*   Internet Explorer